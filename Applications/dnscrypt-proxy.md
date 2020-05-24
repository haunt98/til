# dnscrypt-proxy

| Distribution | Package          |
| ------------ | ---------------- |
| Arch Linux   | `dnscrypt-proxy` |
| Ubuntu       | `dnscrypt-proxy` |

Edit `/etc/dnscrypt-proxy/dnscrypt-proxy.toml`:

```toml
listen_addresses = ['127.0.0.1:53', '[::1]:53']

server_names = ['google', 'google-ipv6', 'cloudflare', 'cloudflare-ipv6']
```

Enable and start service:

```sh
systemctl enable --now dnscrypt-proxy.service
```

In NetworkManager GUI, change DNS:

```txt
IPv4    127.0.0.1
IPv6    ::1
```
