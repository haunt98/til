# OpenVPN

Assume you use Archlinux.

Read [OpenVPN](https://wiki.archlinux.org/index.php/OpenVPN).

Read [The update-systemd-resolved custom script](https://wiki.archlinux.org/index.php/OpenVPN#The_update-systemd-resolved_custom_script).

Read [update-systemd-resolved](https://github.com/jonathanio/update-systemd-resolved).

Read [Connecting To Access Server With Linux](https://openvpn.net/vpn-server-resources/connecting-to-access-server-with-linux/).

Install [openvpn-update-systemd-resolved](https://aur.archlinux.org/packages/openvpn-update-systemd-resolved/).

Start/enable service:

```sh
systemctl start systemd-resolved.service

systemctl enable systemd-resolved.service
```

Edit `client.ovpn`:

```txt
up /etc/openvpn/scripts/update-systemd-resolved
up-restart
down /etc/openvpn/scripts/update-systemd-resolved
down-pre
```

Connect:

```sh
sudo openvpn --config /path/to/client.ovpn --auth-user-pass --auth-retry interact
```
