# Regular expression

Read [Syntax](https://github.com/google/re2/wiki/Syntax).

Read [Golang-Regex-Tutorial](https://github.com/StefanSchroeder/Golang-Regex-Tutorial).

Play with [Regex101](https://regex101.com/).

## Basic

| regex        | meaning                                   |
| ------------ | ----------------------------------------- |
| `.`          | any character, default not including `\n` |
| `[xy]`       | `x` or `y` character                      |
| `[^xy]`      | not `x` and `y` character                 |
| `x`\|`y`     | `x` or `y`                                |
| `x*`         | 0 or more `x`, prefer **more**            |
| `x+`         | 1 or more `x`, prefer **more**            |
| `x?`         | 0 or 1 `x` , prefer 1                     |
| `x*?`        | 0 or more `x`, prefer **fewer**           |
| `x+?`        | 1 or more `x`, prefer **fewer**           |
| `^`          | at beginning of text                      |
| `$`          | at end of text                            |
| `\d`         | digits                                    |
| `\D`         | not digits                                |
| `\s`         | whitespace                                |
| `\S`         | not whitespace                            |
| `(foo)`      | numbered capturing group (submatch)       |
| `(?:foo)`    | non capturing group                       |
| `(?:x`\|`y)` | `x` or `y` expression wrap in `()`        |
| `(?flags)`   | set flags within current group            |

| flag | meaning          |
| ---- | ---------------- |
| `i`  | case-insensitive |
| `s`  | `.` match `\n`   |

## Example

```regex
(?i)hello\sfoo

match: Hello Foo
match: heLLo fOO
```

```regex
hello\s(.+)

match: hello foo
group 1: foo


match: hello bar
group 1: bar
```
