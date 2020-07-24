# Top Down Operator Precedence

Read [Top Down Operator Precedence](https://tdop.github.io/).

Read [Top down operator precedence parsing in Go](http://www.cristiandima.com/top-down-operator-precedence-parsing-in-go/).

Main flow:

```txt
Scanner -> Parser
```

## Scanner

Input: string

Output: series of tokens

Token is type of text.
Example input is `1 + 2`: `1`, `2` is token `int`, `+` is token `plus`.

## Parser

From tokens we scanned, we parsed them to [AST tree](https://en.wikipedia.org/wiki/Abstract_syntax_tree).

### Expression

Each node of AST tree is called expression.
We implement expression like this:

```go
type Expression struct {
  Token    Token
  Value    interface{}
  Children []Expression
}
```

Each expression has `Token`. `Value` and `Children` is optional.
Example: expression `int 3` has `Token int`, `Value 3` but doesn't have `Children`,
expression `and A B` has `Token and`, `Children A B` but doesn't have `Value`.

With input `A + B * C`, we parse to expression like this:

```txt
  +
 / \
A   *
   / \
  B   C
```

### Token precedence

Each token has [precedence](https://en.wikipedia.org/wiki/Order_of_operations#Programming_languages).
Precedence decides order of operator.
Example `A + B * C`, `*` has higher precedence than `+` so `A + (B * C)`.

### Token program

Each token has programs, program to decide what to do if we meet that token when we parse.

Token program can be 2 types: `nud` or `led`.

| short | long            | explain                                                          |
| ----- | --------------- | ---------------------------------------------------------------- |
| `nud` | null denotation | code denoted by a value (int, string, ...) token or prefix token |
| `led` | left denotation | code denoted by an infix token                                   |

Example prefix token is `(`, `not`, `-` (negative sign).
Example infix token is `and`, `or`, `==`.

### Pratt algorithm

To do what we want, we implement Pratt algorithm.

Core algorithm looks like this:

```go
func Parse(precedence int) Expression {
  token := Scan()
  result := nud(token)

  for {
    peekToken := Peek()
    if precedence >= peekToken.Precedence() {
      break
    }

    token := Scan()
    result = led(token, result)
  }

  return result
}

func nud(token Token) Expression {
  return Expression{
    Token: token,
    // deal with value and children
  }
}

func led(token Token, expr Expression) Expression {
  rightExpr := Parse(token.Precedence())
  // do something special
  return Expression {
    Token: token,
    // deal with value
    Children: []Expression{
      expr,
      rightExpr,
    }
  }
}
```

| mystery                                | explain                                                                   |
| -------------------------------------- | ------------------------------------------------------------------------- |
| `precedence argument`                  | precedence of previous token                                              |
| `Scan()`                               | return next token and ahh it gone                                         |
| `Peek()`                               | return next token but it's still there                                    |
| `precedence >= peekToken.Precedence()` | previous token is already powerful than next token, stop                  |
| `nud(token)`                           | return expression, this token must be value or prefix                     |
| `led(token, result)`                   | return expression with result as right argument, this token must be infix |

Must remember is `nud()` and `led` in example are for general.
Each token should define how `nud()` and `led()` do, if not define let user handle error.

To parse, call `Parse(0)`.

This algorithm is hard I know. But it will be easier if we read through example

### Example

Assume `+`, `-` precedence is 1, `*` precedence is 2.

Input: `A + B * C - D`

Function calls happen as follows:

```txt
Parse(precedence = 0) (1)
  nud(A) result in Expression(A)
  0 < peek.Precedence (peek is +, precedence is 1), enter loop
    led(+, Expression(A)) result in Expression(+)
      save Expression(A) as first child
      call Parse(precedence = 1) (2) and save result as second child

Tree:
  +
 / \
A   ?

Parse(precedence = 1) (2)
  nud(B) result in Expression(B)
  1 < peek.Precedence (peek is *, precedence is 2), enter loop
    led(*, Expression(B)) result in Expression(*)
      save Expression(B) as first child
      call Parse(precedence = 2) (3) and save result as second child

Tree:
  *
 / \
B   ?

Parse(precedence = 2) (3)
  nud(C) result in Expression(C)
  2 > peek.Precedence(peek is -, precedence is 1), stop loop
  return Expression(C)

Tree:
C

Back to Parse(precedence = 1) (2)
  Expression(*) has Expression(C) as second child
  continue loop
    1 = peek.Precedence (peek is -, precedence is 1), stop loop
  return Expression(*) with Expression(B), Expression(C) as children

Tree:
  *
 / \
B   C

Back to Parse(precedence = 0) (1)
  Expression(+) has Expression(*) as second child
  continue loop
    0 < peek.Precedence (peek is +, precedence is 1)
      led(-, Expression(+)) result in Expression(-)
      save Expression(+) as first child
      call Parse(precedence = 1) (4) and save result as second child

Tree:
    -
   / \
  +   ?
 / *
A / \
 B   C

Parse(precedence = 1) (4)
  nud(D) result in Expression(D)
  1 < peek.Precedence(peek is EOF, precedence is 0), stop loop
  return Expression(D)

Tree:
D

Back to Parse(precedence = 0) (1)
  Expression(-) has Expression(D) as second child
  continue loop
    0 = peek.Precedence(peek is EOF, precedence is 0), stop loop
  return Expression(-) with Expression(+), Expression(D) as children

Tree:
    -
   / \
  +   D
 / *
A / \
 B   C
```
