# OpenVPN

| Distribution | Package   |
| ------------ | --------- |
| Arch Linux   | `openvpn` |
| Ubuntu       | `openvpn` |

Connect with factor authentication and start as a dameon:

```sh
sudo openvpn --config /path/to/client.ovpn \
    --auth-user-pass --auth-retry interact \
    --daemon
```
