# Go

| Distribution | Package          |
| ------------ | ---------------- |
| Arch Linux   | `go`, `go-tools` |
| Fedora       | `golang`         |
| Snap         | `go`             |

Add to `~/.bashrc`:

```bash
export GOPATH=$HOME/go
export PATH="$PATH:$GOPATH/bin"
```

## Guideline

[CommonMistakes](https://github.com/golang/go/wiki/CommonMistakes)

[CodeReviewComments](https://github.com/golang/go/wiki/CodeReviewComments)

[Uber Go Style Guide](https://github.com/uber-go/guide/blob/master/style.md)

[Thanos Coding Style Guide](https://thanos.io/contributing/coding-style-guide.md/)

## Helpful

[goimports](https://pkg.go.dev/golang.org/x/tools/cmd/goimports?tab=doc)

[GolangCI-Lint](https://github.com/golangci/golangci-lint)

[panicparse](https://github.com/maruel/panicparse)

[gomock](https://github.com/golang/mock)
