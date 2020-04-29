# Use fwupd

Assume you use Archlinux.

Read [fwupd](https://wiki.archlinux.org/index.php/Fwupd).

Install `fwupd`, `gnome-firmware` for GUI.

Download the latest metadata:

```sh
fwupdmgr refresh
```

List updates available:

```sh
fwupdmgr get-updates
```

Install updates:

```sh
fwupdmgr update
```
