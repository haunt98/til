# Go

## Set up

Read [Go](https://wiki.archlinux.org/index.php/Go).

Install:

- [go](https://www.archlinux.org/packages/community/x86_64/go/)
- [go-tools](https://www.archlinux.org/packages/community/x86_64/go-tools/)

Add to `~/.bashrc`, `~/.zshrc`, `~/.config/fish/config.fish`:

```sh
export GOPATH=$HOME/go
export PATH="$PATH:$GOPATH/bin"
```

## Guideline

[CommonMistakes](https://github.com/golang/go/wiki/CommonMistakes)

[CodeReviewComments](https://github.com/golang/go/wiki/CodeReviewComments)

[Uber Go Style Guide](https://github.com/uber-go/guide/blob/master/style.md)

[Thanos Coding Style Guide](https://thanos.io/contributing/coding-style-guide.md/)

## Helpful programs

[goimports](https://pkg.go.dev/golang.org/x/tools/cmd/goimports?tab=doc)

[GolangCI-Lint](https://github.com/golangci/golangci-lint)

[gomodifytags](https://github.com/fatih/gomodifytags)
