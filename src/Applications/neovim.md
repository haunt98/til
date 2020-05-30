# [Neovim](https://github.com/neovim/neovim)

| Distribution | Package  |
| ------------ | -------- |
| Arch Linux   | `neovim` |
| Ubuntu       | `neovim` |
| Homebrew     | `neovim` |

Add to `~/.bashrc`:

```bash
export EDITOR=nvim

# Arch Linux, Ubuntu
[[ -f /usr/bin/nvim ]] && \
    alias vim="nvim"

# Homebrew
[[ -f /usr/local/bin/nvim ]] && \
    alias vim="nvim"
```
