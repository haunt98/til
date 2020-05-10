# [fzf](https://wiki.archlinux.org/index.php/Fzf)

| Distribution | Package |
| ------------ | ------- |
| Archlinux    | `fzf`   |
| Ubuntu       | `fzf`   |

Add to `~/.bashrc`:

```bash
[[ -f /usr/share/fzf/key-bindings.bash ]] && \
    source /usr/share/fzf/key-bindings.bash
[[ -f /usr/share/fzf/completion.bash ]] && \
    source /usr/share/fzf/completion.bash

export FZF_DEFAULT_COMMAND='fd -H'
export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"
```
