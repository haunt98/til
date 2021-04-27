# [systemd-boot](https://wiki.archlinux.org/index.php/Systemd-boot)

Install using XBOOTLDR:

```sh
bootctl --esp-path=/efi --boot-path=/boot install
```

Update everytime systemd is updated:

```sh
bootctl --esp-path=/efi --boot-path=/boot update
```

[Label partition](https://wiki.archlinux.org/index.php/persistent_block_device_naming#by-label)

Edit `/efi/loader/loader.conf`:

```txt
default	archlinux.conf
timeout 4
editor no
console-mode max
```

Edit `/boot/loader/entries/archlinux.conf`:

```txt
title Arch Linux
linux /vmlinuz-linux

# Using Intel
initrd /intel-ucode.img

# Using AMD
initrd /amd-ucode.img

initrd /initramfs-linux.img
options root="LABEL=ROOT" rw
```
