# Install Arch Linux

Install Arch Linux is thing I always want to do for my laptop/PC since I had my laptop in ninth grade.

This is not a guide for everyone, this is just save for myself in a future and for anyone who want to taste a bit.

Assume your laptop/PC is UEFI-capable.

## [Installation guide](https://wiki.archlinux.org/index.php/Installation_guide)

Check disks carefully:

```sh
lsblk
```

[USB flash installation medium](https://wiki.archlinux.org/index.php/USB_flash_installation_medium)

### Connect to the internet

Read [iwd/iwctl](Applications/System/iwd.md).

### Partition the disks

Partition:

```sh
cfdisk
```

| Mount point | Partition type       | Suggested size |
| ----------- | -------------------- | -------------- |
| `/mnt/efi`  | EFI system partition | 512 MiB        |
| `/mnt/boot` | Linux extended boot  | 1 GiB          |
| `/mnt`      | Linux                | 24 GiB         |
| `/mnt/var`  | Linux                | 24 GiB         |
| `/mnt/home` | Linux                |                |

Format:

```sh
# /efi, /boot
mkfs.fat -F32 /dev/sdxY

# /, /var, /home
mkfs.ext4 /dev/sdxY
```

Mount:

```sh
# /
mount /dev/sdxY /mnt

# /efi
mkdir -p /mnt/efi
mount /dev/sdxY /mnt/efi

# /boot
mkdir -p /mnt/boot
mount /dev/sdxY /mnt/boot

# /var
mkdir -p /mnt/var
mount /dev/sdxY /mnt/var

# /home
mkdir -p /mnt/home
mount /dev/sdxY /mnt/home
```

### Installation

```sh
pacstrap /mnt base base-devel linux linux-lts linux-zen linux-firmware neovim
```

Using Intel:

```sh
pacstrap /mnt intel-ucode
```

Using AMD:

```sh
pacstrap /mnt amd-ucode
```

### Boot loader

[systemd-boot](Applications/System/systemd-boot.md)

## [General recommendations](https://wiki.archlinux.org/index.php/General_recommendations)

Always remember to check **dependencies** when install packages.

### System administration

Add user:

```sh
useradd -m -G additional_groups -s login_shell username
```

Set password:

```sh
passwd username
```

Enable sudo:

```sh
EDITOR=nvim visudo

# Uncomment group wheel
```

| Pseudo              | Real        |
| ------------------- | ----------- |
| `additional_groups` | `wheel`     |
| `login_shell`       | `/bin/bash` |
| `username`          | `joker`     |

### Desktop Environment

Install [Xorg](https://wiki.archlinux.org/index.php/Xorg):

```sh
pacman -Syu xorg-server
```

Install [GNOME](https://wiki.archlinux.org/index.php/GNOME):

```sh
pacman -Syu gnome
```

Install [MATE](https://wiki.archlinux.org/index.php/MATE)

```sh
pacman -Syu mate mate-extra
```

Install [Xfce](https://wiki.archlinux.org/index.php/xfce#Installation)

```sh
pacman -Syu xfce4 xfce4-goodies
```

Install and enable [GDM](https://wiki.archlinux.org/index.php/GDM) for GNOME:

```sh
pacman -Syu gdm

systemctl enable gdm.service
```

Install and enable [LightDM](https://wiki.archlinux.org/index.php/LightDM) for MATE, Xfce:

```sh
pacman -Syu lightdm lightdm-gtk-greeter lightdm-gtk-greeter-settings

systemctl enable lightdm.service
```

Install and enable [NetworkManager](https://wiki.archlinux.org/index.php/NetworkManager):

```sh
pacman -Syu networkmanager

# Support OpenVPN
pacman -Syu networkmanager-openvpn

# Support MATE, Xfce
pacman -Suy network-manager-applet

systemctl enable NetworkManager.service
```

Install and enable [Bluetooth](https://wiki.archlinux.org/index.php/Bluetooth):

```sh
pacman -Syu bluez bluez-utils

systemctl enable bluetooth.service
```

Enable [systemd-timesyncd](https://wiki.archlinux.org/index.php/systemd-timesyncd)

```sh
timedatectl set-ntp true
```

## [List of applications](https://wiki.archlinux.org/index.php/List_of_applications)

### [pacman](https://wiki.archlinux.org/index.php/pacman)

Uncomment in `/etc/pacman.conf`:

```txt
# Misc options
Color
```

### [AUR](https://wiki.archlinux.org/index.php/Arch_User_Repository)

Install AUR package:

```sh
makepkg -sric
```

## [Improving performance](https://wiki.archlinux.org/index.php/improving_performance)

[systemd-swap](Applications/System/systemd-swap.md)

[systemd-journald](Applications/System/systemd-journald.md)

[fstrim](Applications/System/fstrim.md)

[earlyoom](Applications/System/earlyoom.md)

[Watchdogs](https://wiki.archlinux.org/index.php/improving_performance#Watchdogs)

[Kernel mode setting](https://wiki.archlinux.org/index.php/kernel_mode_setting)

## In the end

This guide is updated regularly I promise.
