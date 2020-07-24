# [errors](https://golang.org/pkg/errors/)

Wrap error:

```go
err := fmt.Errorf("Something wrong: %w", rootErr)
```

Unwrap error:

```go
rootErr := errors.Unwrap(err)
```
