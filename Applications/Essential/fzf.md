# [fzf](https://github.com/junegunn/fzf)

Should install using git.

Add to `~/.bashrc`, `~/.zshrc`:

```bash
# Use fd instead of find
export FZF_DEFAULT_COMMAND='fd --hidden --exclude .git'
export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"

# Colorscheme
export FZF_DEFAULT_OPTS='--color dark'
export FZF_DEFAULT_OPTS='--color light'
```

| Shorcut  | Explain                              |
| -------- | ------------------------------------ |
| `CTRL-T` | search through files and directories |
| `CTRL-R` | search though command-line history   |

Add to `~/.vimrc`, `~/.config/nvim/init.vim`:

```vim
set rtp+=~/.fzf
```
