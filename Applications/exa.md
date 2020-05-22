# [exa](https://github.com/ogham/exa)

| Distribution | Package    |
| ------------ | ---------- |
| Archlinux    | `exa`      |
| Ubuntu       | `rust-exa` |
| Homebrew     | `exa`      |

Add to `~/.bashrc`:

```bash
# Archlinux, Ubuntu
[[ -f /usr/bin/exa ]] && \
    alias ls="exa"

# Homebrew
[[ -f /usr/local/bin/exa ]] && \
    alias ls="exa"
```
