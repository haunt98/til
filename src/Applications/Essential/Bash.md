# Bash

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

| Shorcut      | Explain                  |
| ------------ | ------------------------ |
| `CTRL-A`     | move to begining of line |
| `CTRL-E`     | move to end of line      |
| `CTRL-Right` | move forward a word      |
| `CTRL-Left`  | move backward a word     |
| `CTRL-W`     | clear the word behind    |

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

## macOS

In macOS, Bash read `~/.bash_profile` not `~/.bashrc`, so edit `~/.bash_profile`:

```bash
[[ -f ~/.bashrc ]] && \
    source ~/.bashrc
```

To use latest Bash, install `bash` with Homebrew.
Then append to `/etc/shells`:

```txt
/usr/local/bin/bash
```

Set default shell

```
chsh -s /usr/local/bin/bash
```
