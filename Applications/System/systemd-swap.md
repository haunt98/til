# [systemd-swap](https://github.com/Nefelim4ag/systemd-swap)

| Distribution | Package        |
| ------------ | -------------- |
| Arch Linux   | `systemd-swap` |
| Fedora       | `systemd-swap` |

Create directory if not exist `/etc/systemd/swap.conf.d` and edit `/etc/systemd/swap.conf.d/overrides.conf`:

```txt
swapfc_enabled=1
```

Enable and start service:

```sh
systemctl enable --now systemd-swap.service
```
