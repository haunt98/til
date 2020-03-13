# OpenVPN

Assume you use Archlinux.

Read [OpenVPN](https://wiki.archlinux.org/index.php/OpenVPN).

Read [The update-systemd-resolved custom script](https://wiki.archlinux.org/index.php/OpenVPN#The_update-systemd-resolved_custom_script).

Read [update-systemd-resolved](https://github.com/jonathanio/update-systemd-resolved).

Install [openvpn-update-systemd-resolved](https://aur.archlinux.org/packages/openvpn-update-systemd-resolved/).

Start/enable service:

```sh
systemctl start systemd-resolved.service

systemctl enable systemd-resolved.service
```

Edit `client.opvn`:

```txt
up /etc/openvpn/scripts/update-systemd-resolved
up-restart
down /etc/openvpn/scripts/update-systemd-resolved
down-pre
```
