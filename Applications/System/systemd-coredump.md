# [systemd-coredump](https://wiki.archlinux.org/index.php/Core_dump#Using_systemd)

Create directory if not exist `/etc/systemd/coredump.conf.d` and edit `/etc/systemd/coredump.conf.d/custom.conf`:

```txt
[Coredump]
Storage=none
```
