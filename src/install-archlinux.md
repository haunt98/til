# Install Arch Linux

Install Arch Linux is thing I always want to do for my laptop/PC since I had my laptop in ninth grade.

This is not a guide for everyone, this is just save for myself in a future and for anyone who want to taste a bit.

Assume your laptop/PC is UEFI-capable.

## [Installation guide](https://wiki.archlinux.org/index.php/Installation_guide)

Check disks carefully:

```sh
lsblk
```

Create USB flash installation media:

```sh
dd bs=4M if=path/to/archlinux.iso of=/dev/sdx status=progress oflag=sync
```

### Connect to the internet

Enable wifi:

```sh
wifi-menu
```

### Partition the disks

Partition:

```sh
cfdisk
```

| Mount point | Partition type       | Suggested size |
| ----------- | -------------------- | -------------- |
| /mnt/boot   | EFI system partition | 512 MiB        |
| /mnt        | Linux                |                |
| /mnt/home   | Linux                |                |

Format:

```sh
# /boot
mkfs.fat -F32 /dev/xxxY

# / and /home
mkfs.ext4 /dev/xxxY
```

### Boot loader

[systemd-boot](https://wiki.archlinux.org/index.php/Systemd-boot)

## [General recommendations](https://wiki.archlinux.org/index.php/General_recommendations)

Always remember to check **dependencies** when install packages.

### System administration

Read [Users and groups](https://wiki.archlinux.org/index.php/Users_and_groups).

Read [Sudo/Using visudo](https://wiki.archlinux.org/index.php/Sudo#Using_visudo).

```sh
useradd -m -G additional_groups -s login_shell username
```

| abstract            | implement   |
| ------------------- | ----------- |
| `additional_groups` | `wheel`     |
| `login_shell`       | `/bin/bash` |

### Graphical user interface and Networking

Install [Xorg](https://wiki.archlinux.org/index.php/Xorg):

```sh
pacman -Syu xorg-server
```

Install [GNOME](https://wiki.archlinux.org/index.php/GNOME):

```sh
pacman -Syu \
    gnome-shell \
    gdm \
    networkmanager gnome-keyring \
    gnome-control-center gnome-tweak-tool \
    nautilus xdg-user-dirs-gtk \
    file-roller p7zip unrar \
    gnome-terminal \
    gnome-backgrounds \
    gnome-screenshot \

```

Enable services:

```sh
systemctl enable gdm.service

systemctl enable NetworkManager.service

timedatectl set-ntp true
```

### Optimization

Read [Solid state drive](https://wiki.archlinux.org/index.php/Solid_state_drive).

Read [Improving performance/Watchdogs](https://wiki.archlinux.org/index.php/Improving_performance#Watchdogs).

Read [Improving performance/Staggered spin-up](https://wiki.archlinux.org/index.php/Improving_performance/Boot_process#Staggered_spin-up).

Read [Silent boot](https://wiki.archlinux.org/index.php/Silent_boot).

### Appearance

Read [Fonts](https://wiki.archlinux.org/index.php/Fonts).

### Misc

[Swap/systemd-swap](https://wiki.archlinux.org/index.php/Swap#systemd-swap)

[systemd/Journal](https://wiki.archlinux.org/index.php/Systemd/Journal)

## [List of applications](https://wiki.archlinux.org/index.php/List_of_applications)

### [pacman](https://wiki.archlinux.org/index.php/pacman)

Uncomment or add if not exist options in `/etc/pacman.conf`:

```txt
# Misc options
Color
ILoveCandy
```

### [AUR](https://wiki.archlinux.org/index.php/Arch_User_Repository)

Install AUR package:

```sh
makepkg -sric
```

## In the end

This guide is updated regularly I promise.