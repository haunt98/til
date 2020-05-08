# Bash

Read [Bash](https://wiki.archlinux.org/index.php/Bash).

Read [Default Keyboard Shortcuts for Bash](https://catonmat.net/ftp/readline-emacs-editing-mode-cheat-sheet.pdf).

Add to `~/.bashrc`:

```bash
export HISTCONTROL=ignoreboth:erasedups
export HISTIGNORE="cd:cd *:ls:ls *:pwd:exit"
```
