# Use git

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

Save usernames and passwords in `~/.git-credentials`:

```sh
git config --global credential.helper store
```

Use `vim` when commit:

```sh
git config --global core.editor vim
```

Rewrite history by changing last `x` commits :

```sh
git rebase -i HEAD~x
```
