# OpenVPN

Read [update-systemd-resolved](https://github.com/jonathanio/update-systemd-resolved).

| Distribution | Package                                 |
| ------------ | --------------------------------------- |
| Arch Linux   | `openvpn-update-systemd-resolved` (AUR) |
| Ubuntu       | `openvpn-systemd-resolved`              |

Start and enable service:

```sh
systemctl enable --now systemd-resolved.service
```

Edit `client.ovpn`:

```txt
script-security 2
setenv PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
up /etc/openvpn/scripts/update-systemd-resolved
up-restart
down /etc/openvpn/scripts/update-systemd-resolved
down-pre
```

Connect with factor authentication and start as a dameon:

```sh
sudo openvpn --config /path/to/client.ovpn \
    --auth-user-pass --auth-retry interact \
    --daemon
```
