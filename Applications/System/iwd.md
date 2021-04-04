# [iwd](https://git.kernel.org/pub/scm/network/wireless/iwd.git/)

| Distribution | Package |
| ------------ | ------- |
| Arch Linux   | `iwd`   |
| Ubuntu       | `iwd`   |

Service: `iwd.service`

After run `iwctl`:

```sh
device list

# Change device to real device
station {device} scan
station {device} get-networks

# Change SSID to real SSID
station {device} connect {SSID}
```

To use NetworkManager, edit `/etc/NetworkManager/conf.d/wifi_backend.conf`

```txt
[device]
wifi.backend=iwd
```
