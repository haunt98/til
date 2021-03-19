# [Neovim](https://github.com/neovim/neovim)

| Distribution | Package  |
| ------------ | -------- |
| Arch Linux   | `neovim` |
| Ubuntu       | `neovim` |
| Homebrew     | `neovim` |

| Shorcut                        | Description                           |
| ------------------------------ | ------------------------------------- |
| `CTRL-N or CTRL-P`             | Insert next, previous matching word   |
| `CTRL-X CTRL-F`                | File completion                       |
| `CTRL-X CTRL-L`                | Line completion                       |
| `CTRL-X CTRL-Q`                | Vim completion                        |
| `CTRL-X CTRL-O`                | Omni completion                       |
| `CTRL-W left, right, up, down` | Go to window in left, right, up, down |
| `CTRL-]`                       | Jump to definition                    |
| `CTRL-O`                       | Jump backwards                        |

## Packages

Autoloaded package is stored `~/.local/share/nvim/site/pack/{foo}/start/{bar}`.

Manually loaded package is stored `~/.local/share/nvim/site/pack/{foo}/opt/{bar}`

`foo` is random name, `bar` is package name.

To load package manully:

```vim
packadd bar
```
