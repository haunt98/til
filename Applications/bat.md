# [bat](https://github.com/sharkdp/bat)

| Distribution | Package    |
| ------------ | ---------- |
| Archlinux    | `bat`      |
| Ubuntu       | `rust-bat` |
| Homebrew     | `bat`      |

Add to `~/.bashrc`:

```bash
# Archlinux, Ubuntu
[[ -f /usr/bin/bat ]] && \
    alias cat="bat"

# Homebrew
[[ -f /usr/local/bin/bat ]] && \
    alias cat="bat"
```
