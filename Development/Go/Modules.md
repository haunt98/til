# [Modules](https://github.com/golang/go/wiki/Modules)

First time:

```sh
go mod init
```

Daily workflow:

```sh
# Update modules
go get -u ./...

# Install module with chosen commit or branch
go get public.git.com/module@branch

# Prune no longer used modules
go mod tidy

# Copy modules to local vendor directory
go mod vendor
```

Outside modules:

```sh
GOMODULE11=on go get example.com/foo/bar
```

Update go version in `go.mod`:

```sh
go mod edit -go-1.xy
```

In world of corporation, we work with private repository, add to `~/.bashrc`, `~/.zshrc`:

```sh
export GOPRIVATE=private.git.com
```
