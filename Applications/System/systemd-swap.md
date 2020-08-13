# [systemd-swap](https://github.com/Nefelim4ag/systemd-swap)

| Distribution | Package        |
| ------------ | -------------- |
| Arch Linux   | `systemd-swap` |

Edit `/etc/systemd/swap.conf`:

```txt
swapfc_enabled=1
swapfc_force_preallocated=1
```

Enable and start service:

```sh
systemctl enable --now systemd-swap.service
```
