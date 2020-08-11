# [Modules](https://github.com/golang/go/wiki/Modules)

First time:

```
go mod init
```

Daily workflow:

```
# Update modules
go get -u ./...

# Install module with chosen commit or branch
go get public.git.com/module@branch

# Prune no longer used modules
go mod tidy

# Copy modules to local vendor directory
go mod vendor
```

In world of corporation, we work with private repository, add to `~/.bashrc`, `~/.zshrc`:

```sh
export GOPRIVATE=private.git.com
```
