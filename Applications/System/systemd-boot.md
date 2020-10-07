# systemd-boot

Read [systemd-boot](https://wiki.archlinux.org/index.php/Systemd-boot).

Install using XBOOTLDR:

```sh
bootctl --esp-path=/efi --boot-path=/boot install
```

Update:

```sh
bootctl update
```

Edit `/efi/loader/loader.conf`:

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

Label partition:

```sh
e2label /dev/xxxY ROOT
```

View partitions:

```sh
blkid
```
