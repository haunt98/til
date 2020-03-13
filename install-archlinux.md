# Install Archlinux

Install Archlinux is thing I always want to do for my laptop/PC since I had my laptop in ninth grade.

This is not a guide for everyone, this is just save for myself in a future and for anyone who want to taste a bit.

Assume your laptop/PC is UEFI-capable.

## [Installation guide](https://wiki.archlinux.org/index.php/Installation_guide)

First [USB flash installation media](https://wiki.archlinux.org/index.php/USB_flash_installation_media).

### Connect to the internet

Enable wifi with `wifi-menu`.

### Partition the disks

Identify:

```sh
lsblk
```

Partition:

```sh
cfdisk
```

- Mount point `/mnt/boot` with `1 GiB`.
- Skip swap because use swap file later.

| Mount point | Partition type                                                                    | Suggested size |
| ----------- | --------------------------------------------------------------------------------- | -------------- |
| /mnt/boot   | [EFI system partition](https://wiki.archlinux.org/index.php/EFI_system_partition) | 1 GiB          |
| /mnt        | Linux                                                                             |                |
| /mnt/home   | Linux                                                                             |

### Boot loader

[systemd-boot](https://wiki.archlinux.org/index.php/Systemd-boot)

## [General recommendations](https://wiki.archlinux.org/index.php/General_recommendations)

Always remember to check dependencies when install packages.

### System administration

Read [Users and groups](https://wiki.archlinux.org/index.php/Users_and_groups):

- Add user with [Zsh](https://wiki.archlinux.org/index.php/Zsh) shell.
- Set password.
- Enable [Sudo](https://wiki.archlinux.org/index.php/Sudo#Using_visudo) access.

### Graphical user interface

Display server: [Xorg](https://wiki.archlinux.org/index.php/Xorg).

Desktop environments: [GNOME](https://wiki.archlinux.org/index.php/GNOME).

Display manager: [GDM](https://wiki.archlinux.org/index.php/GDM), start/enable service:

```sh
systemctl start gdm.service

systemctl enable gdm.service
```

### Networking

Network configuration: [NetworkManager](https://wiki.archlinux.org/index.php/NetworkManager), start/enable service:

```sh
systemctl start NetworkManager.service

systemctl enable NetworkManager.service
```

Clock synchronization: [systemd-timesyncd](https://wiki.archlinux.org/index.php/Systemd-timesyncd):

```sh
timedatectl set-ntp true
```

### Optimization

Read [Solid state drive](https://wiki.archlinux.org/index.php/Solid_state_drive).

Read [Improving performance](https://wiki.archlinux.org/index.php/Improving_performance).

Read [Watchdogs](https://wiki.archlinux.org/index.php/Improving_performance#Watchdogs).

Read [Staggered spin-up](https://wiki.archlinux.org/index.php/Improving_performance/Boot_process#Staggered_spin-up).

Read [Silent boot](https://wiki.archlinux.org/index.php/Silent_boot).

### Appearance

Read [Fonts](https://wiki.archlinux.org/index.php/Fonts).

### Misc

Swap file: [systemd-swap](https://wiki.archlinux.org/index.php/Swap#systemd-swap).

## [List of applications](https://wiki.archlinux.org/index.php/List_of_applications)

## In the end

This is it. Future update is coming if I feel something need to be changed or I get boring and change my taste :)
