# [systemd-swap](https://github.com/Nefelim4ag/systemd-swap)

## Installation

| Distribution | Package        |
| ------------ | -------------- |
| Arch Linux   | `systemd-swap` |
| Fedora       | `systemd-swap` |

Service: `systemd-swap.service`

## Configuration

Create directory if not exist `/etc/systemd/swap.conf.d` and edit `/etc/systemd/swap.conf.d/overrides.conf`:

```txt
swapfc_enabled=1
```

Edit `/etc/sysctl.d/99-swappiness.conf`:

```txt
vm.swappiness=10
```
