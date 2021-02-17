# rsync

| Distribution | Package |
| ------------ | ------- |
| Arch Linux   | `rsync` |
| Debian       | `rsync` |
| Ubuntu       | `rsync` |
| Fedora       | `rsync` |
| Homebrew     | `rsync` |

```sh
rsync -vah src dest
```

`--delete`: Delete files exist in dest but not exist in src.

`--ignore-existing`: Ignore updating existing files in dest.

`--exclude-from=FILE`: Exclude pattern files in FILE.

`-n`: Trial run.
