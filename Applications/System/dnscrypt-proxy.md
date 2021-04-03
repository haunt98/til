# [dnscrypt-proxy](https://github.com/DNSCrypt/dnscrypt-proxy)

## Installation

| Distribution | Package          |
| ------------ | ---------------- |
| Arch Linux   | `dnscrypt-proxy` |
| Ubuntu       | `dnscrypt-proxy` |
| Fedora       | `dnscrypt-proxy` |

Service: `dnscrypt-proxy.service`

## Configuration

Edit `/etc/dnscrypt-proxy/dnscrypt-proxy.toml`:

```toml
listen_addresses = ['127.0.0.1:53', '[::1]:53']

server_names = ['google', 'google-ipv6', 'cloudflare', 'cloudflare-ipv6']
```

In NetworkManager GUI, turn off automatic DNS and edit:

```txt
IPv4    127.0.0.1
IPv6    ::1
```
