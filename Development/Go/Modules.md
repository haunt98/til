# [Modules](https://github.com/golang/go/wiki/Modules)

First time:

```sh
go mod init
```

Daily workflow:

```sh
# Update modules
go get -d -u ./...

# Add module with chosen commit or version
go get -d public.git.com/path/to/module@version

# Build and intall binary with latest version
go install public.git.com/path/to/module@latest

# Prune no longer used modules
go mod tidy

# Copy modules to local vendor directory (vendor is not recommend anymore)
go mod vendor

# Why use module
go mod why -m public.git.com/path/to/module
```

Update go version:

```sh
go mod edit -go=1.XY
```

In world of corporation, we work with private repository, add to `~/.bashrc`, `~/.zshrc`:

```sh
export GOPRIVATE=private.git.com
```

## Thanks

- https://encore.dev/guide/go.mod
