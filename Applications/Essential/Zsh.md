# [Zsh](https://wiki.archlinux.org/index.php/Zsh)

## macOS

To use latest zsh in macOS, install `zsh` with Homebrew.
Then append to `/etc/shells`:

```txt
/usr/local/bin/zsh
```

Set default shell:

```sh
chsh -s /usr/local/bin/zsh
```
