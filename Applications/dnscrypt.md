# DNSCrypt

Assume you use Archlinux and NetworkManager.

Install [dnscrypt-proxy](https://wiki.archlinux.org/index.php/Dnscrypt-proxy).

Edit `/etc/dnscrypt-proxy/dnscrypt-proxy.toml`:

- Change `listen_addresses` option:

```toml
listen_addresses = ['127.0.0.1:53', '[::1]:53']
```

- Change `server_names` option to use Cloudflare:

```toml
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
