# Git

## Config

Aliases:

```sh
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.cl clone
git config --global alias.co checkout
git config --global alias.df diff
git config --global alias.lg log
git config --global alias.pl pull
git config --global alias.ps push
git config --global alias.st status
git config --global alias.sw switch
```

Use nice editor when commit:

```sh
git config --global core.editor <editor>
```

Always pull rebase:

```sh
git config --global pull.rebase true
```

Set default branch to `main`:

```sh
git config --global init.defaultBranch main
```

Always fetch/pull prune:

```sh
git config --global fetch.prune true
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
git rebase -i HEAD~<x>
```

Squash last `x` commits to 1 commit:

```sh
git reset HEAD~<x>
git add -A
git commit
```

Cleanup unnecessary files:

```sh
git gc
```

Find common ancestor:

```sh
git merge-base <A> <B>
```

Log:

```sh
git log --pretty=oneline
git log --graph --pretty=oneline
git log --date=human
```

Changelog:

```sh
git shortlog <commit>..HEAD
```

Clean untracked files and folders:

```sh
git clean -fd

# If afraid
git clean -fdn
```
