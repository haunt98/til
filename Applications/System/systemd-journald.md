# [systemd-journald](https://wiki.archlinux.org/index.php/Systemd/Journal)

Create directory if not exist `/etc/systemd/journald.conf.d` and edit `/etc/systemd/journald.conf.d/00-journal-size.conf`:

```txt
[Journal]
SystemMaxUse=50M
```

Restart service:

```sh
systemctl restart systemd-journald.service
```
