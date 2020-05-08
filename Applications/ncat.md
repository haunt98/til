# Ncat

Assume you use Archlinux.

It is included in [nmap](https://www.archlinux.org/packages/extra/x86_64/nmap/).

Check connectivity to `host` with `port`:

```sh
ncat -zv host post
```

Example:

```sh
ncat -zv google.com 80
```
