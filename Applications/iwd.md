# iwd

Assume you use Archlinux.

Read [iwd](https://wiki.archlinux.org/index.php/Iwd).

Read [NetworkManager: Using iwd as the Wi-Fi backend](https://wiki.archlinux.org/index.php/NetworkManager#Using_iwd_as_the_Wi-Fi_backend).

Edit `/etc/NetworkManager/conf.d/wifi_backend.conf`:

```txt
[device]
wifi.backend=iwd
```
