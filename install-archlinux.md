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

Read [iwd/iwctl](https://wiki.archlinux.org/index.php/Iwd#iwctl):

```sh
iwctl
```

Inside `iwctl`:

```sh
device list

# Change device to real device
station device scan

station device get-networks

# Change SSID to real SSID
station device connect SSID
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

Mount:

```sh
mount /dev/xxxY /mnt

mkdir -p /mnt/boot
mount /dev/xxxY /mnt/boot

mkdir -p /mnt/home
mount /dev/xxxY /mnt/home
```

### Installation

```sh
pacstrap /mnt base base-devel linux linux-firmware man-db man-pages intel-ucode neovim
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
pacman -Syu gnome-shell gdm gnome-control-center gnome-tweak-tool gnome-shell-extensions \
    networkmanager gnome-keyring \
    nautilus xdg-user-dirs-gtk \
    file-roller p7zip unrar \
    gnome-terminal gnome-backgrounds gnome-screenshot \
    evince eog
```

Enable services:

```sh
systemctl enable gdm.service

systemctl enable NetworkManager.service

systemctl enable bluetooth.service

timedatectl set-ntp true
```

## [List of applications](https://wiki.archlinux.org/index.php/List_of_applications)

### [pacman](https://wiki.archlinux.org/index.php/pacman)

Uncomment or add if not exist options in `/etc/pacman.conf`:

```txt
# Misc options
Color
```

### [AUR](https://wiki.archlinux.org/index.php/Arch_User_Repository)

Install AUR package:

```sh
makepkg -sric
```

## In the end

This guide is updated regularly I promise.
