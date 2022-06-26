# [chrony](https://git.tuxfamily.org/chrony/chrony.git)

| Distribution | Package  |
| ------------ | -------- |
| Arch Linux   | `chrony` |
| Ubuntu       | `chrony` |

## Network Time Security

https://developers.cloudflare.com/time-services/nts/

https://system76.com/time

Edit `/etc/chrony/chrony.conf`:

```txt
server time.cloudflare.com iburst nts
server virginia.time.system76.com iburst nts
server ohio.time.system76.com iburst nts
server oregon.time.system76.com iburst nts
```

Verify:

```sh
chronyc sources -v
sudo chronyc authdata -v
```
