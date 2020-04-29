# systemd-boot

Read [systemd-boot](https://wiki.archlinux.org/index.php/Systemd-boot).

Assume you use Archlinux, and [EFI system partition](https://wiki.archlinux.org/index.php/EFI_system_partition) mount point is `/boot`.

Install:

```sh
bootctl --path=/boot install
```

Update:

```sh
bootctl update
```

Edit `/boot/loader/loader.conf`:

```txt
default         archlinux.conf
timeout         4
console-mode    max
editor          no
```

Edit `/boot/loader/entries/archlinux.conf`:

```txt
title       Arch Linux
linux       /vmlinuz-linux
initrd      /intel-ucode.img
initrd      /initramfs-linux.img
options     root="LABEL=ROOT" rw
```

Label root partition:

```sh
e2label /dev/XXX ROOT
```

View partitions:

```sh
blkid
```
