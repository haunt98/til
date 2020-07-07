# Git

| Distribution | Package |
| ------------ | ------- |
| Arch Linux   | `git`   |
| Ubuntu       | `git`   |

## Config

Aliases:

```sh
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.co checkout
git config --global alias.df diff
git config --global alias.st status
git config --global alias.logo 'log --pretty=oneline'
```

Save usernames and passwords in `~/.git-credentials`:

```sh
git config --global credential.helper store
```

Use neovim when commit:

```sh
git config --global core.editor nvim
```

## Commands

Prefer rebase when pull:

```sh
git pull --rebase
```

Clean outdated branches:

```sh
git fetch --prune
```

Push force **safely**:

```sh
git push --force-with-lease
```

Rewrite history by changing last `x` commits :

```sh
git rebase -i HEAD~x
```
