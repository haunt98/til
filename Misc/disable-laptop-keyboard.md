# Disable laptop keyboard

Why? Because I want to place my mechanical keyboard over my laptop keyboard.

Read [Xinput](https://wiki.archlinux.org/index.php/Xinput) carefully.

Disable:

```sh
xinput float "AT Translated Set 2 keyboard"
```

Enable:

```sh
xinput reattach "AT Translated Set 2 keyboard" 3
```
