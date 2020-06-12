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

## Packages

Autoloaded package is stored `~/.local/share/nvim/site/pack/{foo}/start/{bar}`.

Manually loaded package is stored `~/.local/share/nvim/site/pack/{foo}/opt/{bar}`

`foo` is random name, `bar` is package name.

To load package manully:

```vim
packadd bar
```
