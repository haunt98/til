# [systemd-journald](https://wiki.archlinux.org/index.php/Systemd/Journal)

Service: `systemd-journald.service`

Remember to restart service after editing.

Create directory if not exist `/etc/systemd/journald.conf.d` and edit `/etc/systemd/journald.conf.d/00-journal-size.conf`:

```txt
[Journal]
SystemMaxUse=50M
```
