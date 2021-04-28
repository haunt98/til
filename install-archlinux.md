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

Use [iwd](https://wiki.archlinux.org/index.php/Iwd).

#### Update the system clock

```sh
timedatectl set-ntp true
```

#### Partition the disks

Partition:

```sh
# For convert GPT
cgdisk

# For easy partition
cfdisk
```

[Partition scheme](https://wiki.archlinux.org/index.php/Partitioning#Partition_scheme)

UEFI/GPT layout:

| Mount point | Partition type       | Suggested size |
| ----------- | -------------------- | -------------- |
| `/mnt/efi`  | EFI system partition | 512 MiB        |
| `/mnt/boot` | Linux extended boot  | 1 GiB          |
| `/mnt`      | Linux                |                |
| `/mnt/var`  | Linux                | >= 12 GiB      |
| `/mnt/home` | Linux                |                |
|             | Linux swap           | RAM x 2        |

Format:

```sh
# efi
mkfs.fat -F32 /dev/efi_system_partition

# boot
mkfs.fat -F32 /dev/boot_system_partition

# root
mkfs.ext4 -L ROOT /dev/root_partition
mkfs.btrfs -L ROOT /dev/root_partition

# var
mkfs.ext4 -L VAR /dev/var_partition
mkfs.btrfs -L VAR /dev/var_partition

# home
mkfs.ext4 -L HOME /dev/home_partition
mkfs.btrfs -L HOME /dev/home_partition

# swap
mkswap /dev/sdxY
```

Mount:

```sh
# root
mount /dev/root_partition /mnt
# btrfs
mount -o compress=zstd /dev/root_partition /mnt

# efi
mkdir /mnt/efi
mount /dev/efi_system_partition /mnt/efi

# boot
mkdir /mnt/boot
mount /dev/boot_system_partition /mnt/boot

# var
mkdir /mnt/var
mount /dev/var_partition /mnt/var
# btrfs
mount -o compress=zstd /dev/var_partition /mnt/var

# home
mkdir /mnt/home
mount /dev/home_partition /mnt/home
# btrfs
mount -o compress=zstd /dev/home_partition /mnt/home

# swap
swapon /dev/swap_partition
```

### Installation

```sh
pacstrap /mnt base linux linux-firmware

# LTS
pacstrap /mnt linux-lts

# Performance
pacstrap /mnt linux-zen

# AMD
pacstrap /mnt amd-ucode

# Intel
pacstrap /mnt intel-ucode

# Btrfs
pacstrap /mnt btrfs-progs

# Text editor
pacstrap /mnt neovim

# Development
pacstrap /mnt base-devel
```

### Configure

#### [fstab](https://wiki.archlinux.org/index.php/Fstab)

```sh
genfstab -U /mnt >> /mnt/etc/fstab
```

https://wiki.archlinux.org/index.php/Fstab#Automount_with_systemd

https://wiki.archlinux.org/index.php/Btrfs#Compression

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
127.0.0.1 localhost
::1 localhost
127.0.1.1 myhostname.localdomain myhostname
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

#### [Users and groups](https://wiki.archlinux.org/index.php/users_and_groups)

Add user:

```sh
useradd -m -G wheel -s /bin/bash -c "The Joker" joker
```

Set password:

```sh
passwd username
```

#### [systemd-homed](https://wiki.archlinux.org/index.php/Systemd-homed)

```sh
systemctl enable systemd-homed.service

homectl create joker --real-name="The Joker" --member-of=wheel
```

#### [Sudo](https://wiki.archlinux.org/index.php/sudo)

```sh
pacman -Syu sudo

EDITOR=nvim visudo
# Uncomment group wheel
```

### Desktop Environment

Install [Xorg](https://wiki.archlinux.org/index.php/Xorg):

```sh
pacman -Syu xorg-server
```

#### [GNOME](https://wiki.archlinux.org/index.php/GNOME)

```sh
pacman -Syu gnome-shell \
	gdm \
	networkmanager \
	gnome-control-center \
	gnome-terminal gnome-backgrounds gnome-screenshot \
	gnome-system-monitor gnome-keyring \
	nautilus xdg-user-dirs-gtk file-roller \
	evince eog gedit

# Login manager
systemctl enable gdm.service

# Network
systemctl enable NetworkManager.service

# Bluetooth
systemctl enable bluetooth.service

# Clock
timedatectl set-ntp true
```

## [List of applications](https://wiki.archlinux.org/index.php/List_of_applications)

### [pacman](https://wiki.archlinux.org/index.php/pacman)

Uncomment in `/etc/pacman.conf`:

```txt
# Misc options
Color
```

## [Improving performance](https://wiki.archlinux.org/index.php/improving_performance)

https://wiki.archlinux.org/index.php/swap#Swappiness

https://wiki.archlinux.org/index.php/Systemd/Journal#Journal_size_limit

https://wiki.archlinux.org/index.php/Core_dump#Disabling_automatic_core_dumps

https://wiki.archlinux.org/index.php/Solid_state_drive#Periodic_TRIM

https://wiki.archlinux.org/index.php/Improving_performance#Improving_system_responsiveness_under_low-memory_conditions

https://wiki.archlinux.org/index.php/improving_performance#Watchdogs

https://wiki.archlinux.org/index.php/Improving_performance/Boot_process#Staggered_spin-up

https://wiki.archlinux.org/index.php/Silent_boot

## In the end

This guide is updated regularly I promise.
