# [efibootmgr](https://github.com/rhboot/efibootmgr)

| Distribution | Package      |
| ------------ | ------------ |
| Arch Linux   | `efibootmgr` |
| Ubuntu       | `efibootmgr` |
| Fedora       | `efibootmgr` |

Display current Boot Manager settings:

```sh
efibootmgr -v
```

Delete boot entry 7th:

```sh
efibootmgr -b 7 -B
```
