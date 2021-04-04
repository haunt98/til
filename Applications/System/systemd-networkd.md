# [systemd-networkd](https://wiki.archlinux.org/index.php/systemd-networkd)

## Installation

Service: `systemd-networkd.service`

Need [systemd-resolved](Applications/System/systemd-resolved.md).

## Configuration

Wired adapter, edit `/etc/systemd/network/20-wired.network`:

```txt
[Match]
Name=en*

[Network]
DHCP=yes

[DHCP]
RouteMetric=10
```

Wireless adapter, edit `/etc/systemd/network/25-wireless.network`:

```txt
[Match]
Name=wl*

[Network]
DHCP=yes

[DHCP]
RouteMetric=20
```

For wireless adapter, need [iwd](Applications/System/iwd.md).
