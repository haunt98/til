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

Update go version:

```sh
go mod edit -go=1.XY
```

In world of corporation, we work with private repository, add to `~/.bashrc`, `~/.zshrc`:

```sh
export GOPRIVATE=private.git.com
```
