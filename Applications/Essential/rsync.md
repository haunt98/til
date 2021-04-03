# rsync

## Installation

| Distribution | Package |
| ------------ | ------- |
| Arch Linux   | `rsync` |
| Ubuntu       | `rsync` |

## Usage

```sh
rsync -vah src dest
```

`--delete`: Delete files exist in dest but not exist in src.

`--ignore-existing`: Ignore updating existing files in dest.

`--exclude-from=FILE`: Exclude pattern files in FILE.

`-n`: Trial run.
