| Distribution | Package          |
| ------------ | ---------------- |
| Arch Linux   | `go`, `go-tools` |

Add to `~/.bashrc`, `~/.zshrc`:

```sh
export GOPATH=$HOME/go
export PATH="$PATH:$GOPATH/bin"
```

## Guideline

[Effective Go](https://go.dev/doc/effective_go)

[CommonMistakes](https://github.com/golang/go/wiki/CommonMistakes)

[CodeReviewComments](https://github.com/golang/go/wiki/CodeReviewComments)

[Uber Go Style Guide](https://github.com/uber-go/guide/blob/master/style.md)

## Helpful libraries

- https://github.com/matryer/moq
- https://github.com/golang/mock
- https://github.com/stretchr/testify
- https://github.com/mvdan/gofumpt
- https://github.com/golangci/golangci-lint
- https://github.com/fatih/vim-go
