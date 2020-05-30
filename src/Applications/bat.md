# [bat](https://github.com/sharkdp/bat)

| Distribution | Package    |
| ------------ | ---------- |
| Arch Linux   | `bat`      |
| Ubuntu       | `rust-bat` |
| Homebrew     | `bat`      |

Add to `~/.bashrc`:

```bash
# Arch Linux, Ubuntu
[[ -f /usr/bin/bat ]] && \
    alias cat="bat"

# Homebrew
[[ -f /usr/local/bin/bat ]] && \
    alias cat="bat"
```
