# [systemd-coredump](https://wiki.archlinux.org/index.php/Core_dump#Using_systemd)

Edit `/etc/systemd/coredump.conf.d/custom.conf`:

```txt
[Coredump]
Storage=none
```
