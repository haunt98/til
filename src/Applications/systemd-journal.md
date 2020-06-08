# systemd/Journal

Edit `/etc/systemd/journald.conf.d/00-journal-size.conf`:

```txt
[Journal]
SystemMaxUse=50M
```

After editing, restart service:

```sh
systemctl restart systemd-journald.service
```
