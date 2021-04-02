# [systemd-networkd](https://wiki.archlinux.org/index.php/systemd-networkd)

## Installation

Service: `systemd-networkd.service`

Enable:

```sh
systemctl enable systemd-networkd.service
```

Need [systemd-resolved](Applications/System/systemd-resolved.md).

## Configuration

After editing, remember to restart service.

Wired adapter, edit `/etc/systemd/network/20-wired.network`:

```txt
[Match]
Name=en*

[Network]
DHCP=yes
```

Wireless adapter, edit `/etc/systemd/network/25-wireless.network`:

```txt
[Match]
Name=wl*

[Network]
DHCP=yes
```
