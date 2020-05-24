# Git

| Distribution | Package |
| ------------ | ------- |
| Arch Linux   | `git`   |
| Ubuntu       | `git`   |

Save usernames and passwords in `~/.git-credentials`:

```sh
git config --global credential.helper store
```

Use neovim when commit:

```sh
git config --global core.editor nvim
```

Prefer rebase when pull:

```sh
git pull --rebase
```

Clean outdated branches:

```sh
git fetch --prune
```

Push force safely:

```sh
git push --force-with-lease
```

Rewrite history by changing last `x` commits :

```sh
git rebase -i HEAD~x
```
