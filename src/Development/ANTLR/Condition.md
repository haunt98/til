# Condition

```antlr4
grammar Condition;

ADD: '+';
SUB: '-';
MUL: '*';
DIV: '/';
MOD: '%';

EQ: '==';
NEQ: '!=';
LT: '<';
LTE: '<=';
GT: '>';
GTE: '>=';
NOT: '!';

AND: [Aa] [Nn] [Dd];
OR: [Oo] [Rr];
IN: [Ii] [Nn];
NOTIN: [Nn] [Oo] [Tt] [Ii] [Nn];

LEFT_PAREN: '(';
RIGHT_PAREN: ')';
LEFT_BRACKET: '[';
RIGHT_BRACKET: ']';

UNDERSCORE: '_';
DOUBLE_QUOTE: '"';
DOLLAR: '$';
COMMA: ',';
POINT: '.';

WHITESPACE: [ \t\n\r]+ -> skip;

fragment DIGIT: [0-9];
fragment LETTER: [a-zA-Z];

TRUE_LITERAL
    : [Tt] [Rr] [Uu] [Ee]
    ;
FALSE_LITERAL
    : [Ff] [Aa] [Ll] [Ss] [Ee]
    ;
FLOAT_LITERAL
    : DIGIT+ (POINT DIGIT+)
    ;
INT_LITERAL
    : DIGIT+
    ;
STRING_LITERAL
    : DOUBLE_QUOTE (~['"\n])*? DOUBLE_QUOTE
    ;

VAR
    : DOLLAR (LETTER | DIGIT | UNDERSCORE)+
    ;

start: expression EOF;

expression
    : LEFT_PAREN expression RIGHT_PAREN # Paren
    | LEFT_BRACKET elements+=expression (COMMA elements+=expression)* RIGHT_BRACKET # Array
    | TRUE_LITERAL # TrueLiteral
    | FALSE_LITERAL # FalseLiteral
    | FLOAT_LITERAL # FloatLiteral
    | INT_LITERAL # IntLiteral
    | STRING_LITERAL # StringLiteral
    | VAR # Var
    | operator=(NOT | ADD | SUB) expression # Unary
    | expression operator=(MUL | DIV | MOD) expression # Binary
    | expression operator=(ADD | SUB) expression # Binary
    | expression operator=(EQ | NEQ | LT | LTE | GT | GTE | IN | NOTIN) expression # Binary
    | expression operator=AND expression # Binary
    | expression operator=OR expression # Binary
    ;
```
