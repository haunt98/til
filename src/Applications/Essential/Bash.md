# Bash

Read [Default Keyboard Shortcuts for Bash](https://catonmat.net/ftp/readline-emacs-editing-mode-cheat-sheet.pdf).

In macOS, Bash read `~/.bash_profile` not `~/.bashrc`, so edit `~/.bash_profile`:

```bash
[[ -f ~/.bashrc ]] && \
    source ~/.bashrc
```

Add to `~/.bashrc`:

```bash
export HISTSIZE=10000
export HISTFILESIZE=10000
export HISTCONTROL=ignoreboth:erasedups
export HISTIGNORE="cd:ls:la:ll:pwd:exit"

shopt -s histappend
```

Shebang:

```sh
#!/usr/bin/env bash
```

## Bash completion

| Distribution | Package           |
| ------------ | ----------------- |
| Arch Linux   | `bash-completion` |
| Ubuntu       | `bash-completion` |
| Homebrew     | `bash-completion` |

Add to `~/.bashrc`:

```bash
# Arch Linux, Ubuntu
[[ -f /usr/share/bash-completion/bash_completion ]] && \
    source /usr/share/bash-completion/bash_completion

# Homebrew
[[ -f /usr/local/etc/bash_completion ]] && \
    source /usr/local/etc/bash_completion
```
