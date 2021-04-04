# [mpv](https://github.com/mpv-player/mpv)

## Installation

| Distribution | Package |
| ------------ | ------- |
| Arch Linux   | `mpv`   |
| Ubuntu       | `mpv`   |

## Usage

### Options

| Option            | Description   |
| ----------------- | ------------- |
| `--no-video`      | Disable video |
| `--shuffle`       | Play random   |
| `--loop-playlist` | Loop playlist |
| `--loop`          | Loop single   |

### Youtube

Need [youtube-dl](Applications/Misc/youtube-dl.md):

Play youtube in terminal:

```sh
mpv "https://www.youtube.com/watch?v=PLACEBO" --no-video

mpv "https://www.youtube.com/playlist?list=PLACEBO" --no-video
```
