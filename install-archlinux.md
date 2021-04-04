# Install Arch Linux

Install Arch Linux is thing I always want to do for my laptop/PC since I had my laptop in ninth grade.

This is not a guide for everyone, this is just save for myself in a future and for anyone who want to taste a bit.

Assume your laptop/PC is UEFI-capable.

## [Installation guide](https://wiki.archlinux.org/index.php/Installation_guide)

### Pre-installation

Check disks carefully:

```sh
lsblk
```

[USB flash installation medium](https://wiki.archlinux.org/index.php/USB_flash_installation_medium)

#### Verify the boot mode

Check UEFI mode:

```sh
ls /sys/firmware/efi/efivars
```

#### Connect to the internet

Use [iwd](Applications/System/iwd.md).

#### Update the system clock

```sh
timedatectl set-ntp true
```

#### Partition the disks

Partition:

```sh
# For convert GPT
cgdisk

cfdisk
```

| Mount point | Partition type       | Suggested size |
| ----------- | -------------------- | -------------- |
| `/mnt/efi`  | EFI system partition | 512 MiB        |
| `/mnt/boot` | Linux extended boot  | 1 GiB          |
| `/mnt`      | Linux                |                |
| `/mnt/home` | Linux                |                |
|             | Linux swap           | RAM x 2        |

Format:

```sh
# efi
mkfs.fat -F32 /dev/efi_system_partition

# boot
mkfs.fat -F32 /dev/boot_system_partition

# root
mkfs.ext4 /dev/root_partition

# home
mkfs.ext4 /dev/home_partition

# swap
mkswap /dev/sdxY
```

Mount:

```sh
# root
mount /dev/root_partition /mnt

# efi
mkdir /mnt/efi
mount /dev/efi_system_partition /mnt/efi

# boot
mkdir /mnt/boot
mount /dev/boot_system_partition /mnt/boot

# home
mkdir /mnt/home
mount /dev/home_partition /mnt/home

# swap
swapon /dev/swap_partition
```

### Installation

```sh
pacstrap /mnt base linux linux-firmware neovim

# LTS
pacstrap /mnt linux-lts

# Performance
pacstrap /mnt linux-zen

# Developement
pacstrap /mnt base-devel

# AMD
pacstrap /mnt amd-ucode

# Intel
pacstrap /mnt intel-ucode

# Documentation
pacstrap /mnt man-db man-pages
```

### Configure

#### Fstab

```sh
genfstab -U /mnt >> /mnt/etc/fstab
```

#### Chroot

```sh
arch-chroot /mnt
```

#### Time zone

```sh
ln -sf /usr/share/zoneinfo/Region/City /etc/localtime

hwclock --systohc
```

#### Localization:

Edit `/etc/locale.gen`:

```txt
# Uncomment en_US.UTF-8 UTF-8
```

Generate locales:

```sh
locale-gen
```

Edit `/etc/locale.conf`:

```txt
LANG=en_US.UTF-8
```

#### Network configuration

Edit `/etc/hostname`:

```txt
myhostname
```

Edit `/etc/hosts`:

```txt
127.0.0.1		localhost
::1					localhost
127.0.1.1		myhostname.localdomain myhostname
```

#### Root password

```sh
passwd
```

#### Boot loader

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

# AMD
pacman -Syu xf86-video-amdgpu mesa

# Intel
pacman -Syu xf86-video-intel mesa

# NVIDIA
pacman -Syu xf86-video-nouveau mesa
```

#### [GNOME](https://wiki.archlinux.org/index.php/GNOME)

```sh
pacman -Syu gnome gdm

# Login manager
systemctl enable gdm.service
```

#### [i3](https://wiki.archlinux.org/index.php/i3)

```sh
pacman -Syu i3-wm i3lock i3status rofi \
	xorg-xinit lxappearance \
	feh archlinux-wallpaper \
	alacritty
```

### [XDG user directories](https://wiki.archlinux.org/index.php/XDG_user_directories)

```sh
pacman -Syu xdg-user-dirs

xdg-user-dirs-update
```

#### [Sound system](https://wiki.archlinux.org/index.php/Sound_system)

[ALSA](https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture):

```sh
pacman -Syu alsa-utils

# https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture#Unmute_with_alsamixer
alsamixer
```

[PulseAudio](https://wiki.archlinux.org/index.php/PulseAudio):

```sh
pacman -Syu pulseaudio pulseaudio-alsa pulseaudio-bluetooth
```

#### Network managers

Use [NetworkManager](Applications/System/NetworkManager.md).

Use [systemd-networkd](Applications/System/systemd-networkd.md).

#### [Bluetooth](https://wiki.archlinux.org/index.php/Bluetooth)

```sh
pacman -Syu bluez bluez-utils

systemctl enable bluetooth.service
```

Use [Blueman](Applications/System/Blueman.md).

#### Clock synchronization

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

[systemd-coredump](Applications/System/systemd-coredump.md)

[fstrim](Applications/System/fstrim.md)

[earlyoom](Applications/System/earlyoom.md)

[Profile-sync-daemon](Applications/System/Profile-sync-daemon.md)

[Watchdogs](https://wiki.archlinux.org/index.php/improving_performance#Watchdogs)

[Staggered spin-up](https://wiki.archlinux.org/index.php/Improving_performance/Boot_process#Staggered_spin-up)

[Silent boot](https://wiki.archlinux.org/index.php/Silent_boot)

[Hardware video acceleration](https://wiki.archlinux.org/index.php/Hardware_video_acceleration)

[Kernel mode setting](https://wiki.archlinux.org/index.php/Kernel_mode_setting)

[Turn off CPU exploit mitigations](https://wiki.archlinux.org/index.php/improving_performance#Turn_off_CPU_exploit_mitigations)

## In the end

This guide is updated regularly I promise.
