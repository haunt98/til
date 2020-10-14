# [Modules](https://github.com/golang/go/wiki/Modules)

First time:

```sh
go mod init
```

Daily workflow:

```sh
# Update modules
go get -u ./...

# Install module with chosen commit or version
go get public.git.com/module@version

# Prune no longer used modules
go mod tidy

# Copy modules to local vendor directory
go mod vendor
```

Outside modules:

```sh
GOMODULE11=on go get example.com/foo/bar
```

Update go version:

```sh
go mod edit -go=1.XY
```

Replace module path and version pair:

```sh
go mod edit -replace old[@v]=new[@v]
```

Drop replace module path:

```sh
go mod edit -dropreplace old[@v]
```

In world of corporation, we work with private repository, add to `~/.bashrc`, `~/.zshrc`:

```sh
export GOPRIVATE=private.git.com
```
