# [efibootmgr](https://github.com/rhboot/efibootmgr)

## Installation

| Distribution | Package      |
| ------------ | ------------ |
| Arch Linux   | `efibootmgr` |
| Ubuntu       | `efibootmgr` |
| Fedora       | `efibootmgr` |

## Usage

Display current Boot Manager settings:

```sh
efibootmgr -v
```

Delete boot entry 7th:

```sh
efibootmgr -b 7 -B
```
