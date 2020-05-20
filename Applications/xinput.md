# Xinput

| Distribution | Package       |
| ------------ | ------------- |
| Archlinux    | `xorg-xinput` |
| Ubuntu       | `xinput`      |

List devices:

```sh
xinput list
```

Usually laptop's keyboard is:

```txt
AT Translated Set 2 keyboard    id=15   [slave  keyboard (3)]
```

Disable laptop's keyboard:

```sh
xinput float "AT Translated Set 2 keyboard"
```

Re-enable laptop's keyboard, `3` is from `slave keyboard (3)`:

```sh
xinput reattach "AT Translated Set 2 keyboard" 3
```
