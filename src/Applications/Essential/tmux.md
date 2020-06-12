# tmux

| distribution | package |
| ------------ | ------- |
| Arch Linux   | `tmux`  |
| Ubuntu       | `tmux`  |

Imagine you want to run a long task in terminal, but you don't want to keep terminal open.

Run the task in tmux then detach session, after some time attach that session.

Show list of tmux sessions:

```sh
tmux ls
```

Attach to tmux session 0:

```sh
tmux attach -t 0
```
