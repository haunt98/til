# [mpv](https://github.com/mpv-player/mpv)

| Distribution | Package |
| ------------ | ------- |
| Arch Linux   | `mpv`   |
| Ubuntu       | `mpv`   |
| Homebrew     | `mpv`   |

## Options

| Option            | Description   |
| ----------------- | ------------- |
| `--no-video`      | Disable video |
| `--shuffle`       | Play random   |
| `--loop-playlist` | Loop playlist |
| `--loop`          | Loop single   |

## Youtube

Require [youtube-dl](https://github.com/ytdl-org/youtube-dl):

| Distribution | Package      |
| ------------ | ------------ |
| Arch Linux   | `youtube-dl` |
| Ubuntu       | `youtube-dl` |
| Homebrew     | `youtube-dl` |

Play youtube in terminal:

```sh
mpv "https://www.youtube.com/watch?v=PLACEBO" --no-video

mpv "https://www.youtube.com/playlist?list=PLACEBO" --no-video
```
