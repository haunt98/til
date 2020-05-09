# Bash

Read [Default Keyboard Shortcuts for Bash](https://catonmat.net/ftp/readline-emacs-editing-mode-cheat-sheet.pdf).

Bash completion:

| Distribution | Package           |
| ------------ | ----------------- |
| Archlinux    | `bash-completion` |
| Ubuntu       | `bash-completion` |

Add to `~/.bashrc`:

```bash
export HISTCONTROL=ignoreboth:erasedups
export HISTIGNORE="cd:cd *:ls:ls *:pwd:exit"

[[ -f /usr/share/bash-completion/bash_completion ]] & \
    source /usr/share/bash-completion/bash_completion
```
