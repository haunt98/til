# [fzf](https://wiki.archlinux.org/index.php/Fzf)

| Distribution | Package |
| ------------ | ------- |
| Archlinux    | `fzf`   |
| Ubuntu       | `fzf`   |
| Homebrew     | `fzf`   |

Add to `~/.bashrc`:

```bash
# Archlinux, Ubuntu
[[ -f /usr/share/fzf/completion.bash ]] && \
    source /usr/share/fzf/completion.bash
[[ -f /usr/share/fzf/key-bindings.bash ]] && \
    source /usr/share/fzf/key-bindings.bash

# Homebrew
[[ -f /usr/local/opt/fzf/shell/completion.bash ]] && \
    source /usr/local/opt/fzf/shell/completion.bash
[[ -f /usr/local/opt/fzf/shell/key-bindings.bash ]] && \
    source /usr/local/opt/fzf/shell/key-bindings.bash

# Use fd instead of find
export FZF_DEFAULT_COMMAND='fd --hidden --exclude .git'
export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"
```

| Shorcut  | Explain                              |
| -------- | ------------------------------------ |
| `CTRL-T` | search through files and directories |
| `CTRL-R` | search though command-line history   |
