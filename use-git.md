# Use git

Prefer rebase when pull:

```sh
git pull --rebase
```

Clean outdated branches:

```sh
git fetch --prune origin
```

Push force safely:

```sh
git push --force-with-lease origin master
```

Shallow clone:

```sh
git clone --depth 1 ...
```

Add submodule:

```sh
git submodule add --depth 1 ...
```

First time pull repo with submodules:

```sh
git submodule update --init --recursive
```

Update submodules:

```sh
git submodule update --recursive --remote
```
