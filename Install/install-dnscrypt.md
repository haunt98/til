# Install DNSCrypt

What is DNSCrypt? Why use DNSCrypt? These questions can be answered by simple Google search, and I don't know where to start.

This guide is thing I save for myself, so be careful.

---

Assume you use Archlinux and NetworkManager, because I use those.

Read [dnscrypt-proxy](https://wiki.archlinux.org/index.php/Dnscrypt-proxy).
Read [dnsmasq](https://wiki.archlinux.org/index.php/Dnsmasq).
Read [NetworkManager](https://wiki.archlinux.org/index.php/NetworkManager).

---

Install dnscrypt-proxy, dnsmasq.

Edit `/etc/dnscrypt-proxy/dnscrypt-proxy.toml`:

- Change `listen_addresses` option:

```toml
listen_addresses = ['127.0.0.1:53000', '[::1]:53000']
```

- Change `server_names` option to use Cloudflare:

```toml
server_names = ['cloudflare', 'cloudflare-ipv6']
```

Edit `/etc/resolv.conf`:

```txt
nameserver ::1
nameserver 127.0.0.1
options edns0 single-request-reopen
```

Edit `/etc/dnsmasq.conf`:

```txt
no-resolv
server=::1#53000
server=127.0.0.1#53000
listen-address=::1,127.0.0.1
cache-size=1000
```

Edit `/etc/NetworkManager/conf.d/dns.conf` to prevent NetworkManager change `/etc/resolv.conf`:

```txt
[main]
dns=none
```

Finally, restart `NetworkManager.service` and start/enable `dnscrypt-proxy.service`, `dnsmasq.service`.
