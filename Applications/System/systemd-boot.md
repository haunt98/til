# [systemd-boot](https://wiki.archlinux.org/index.php/Systemd-boot)

Install using XBOOTLDR:

```sh
bootctl --esp-path=/efi --boot-path=/boot install
```

Update:

```sh
bootctl update
```

Label partition:

```sh
e2label /dev/xxxY ROOT
```

View partitions:

```sh
blkid
```

Edit `/efi/loader/loader.conf`:

```txt
default         archlinux.conf
timeout         4
editor          no
console-mode    max
```

Edit `/boot/loader/entries/archlinux.conf`:

```txt
title       Arch Linux
linux       /vmlinuz-linux
# Using Intel
initrd      /intel-ucode.img
# Using AMD
initrd      /amd-ucode.img
initrd      /initramfs-linux.img
options     root="LABEL=ROOT" rw
```

Edit `/boot/loader/entries/archlinux-lts.conf`:

```txt
title       Arch Linux LTS
linux       /vmlinuz-linux-lts
# Using Intel
initrd      /intel-ucode.img
# Using AMD
initrd      /amd-ucode.img
initrd      /initramfs-linux-lts.img
options     root="LABEL=ROOT" rw
```

Edit `/boot/loader/entries/archlinux-zen.conf`:

```txt
title       Arch Linux ZEN
linux       /vmlinuz-linux-zen
# Using Intel
initrd      /intel-ucode.img
# Using AMD
initrd      /amd-ucode.img
initrd      /initramfs-linux-zen.img
options     root="LABEL=ROOT" rw
```
