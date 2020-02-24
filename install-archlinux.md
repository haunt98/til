# Install Archlinux

Install Archlinux is thing I always want to do for my laptop/PC since I had my laptop in ninth grade.

This is not a guide for everyone, this is just save for myself in a future and for anyone who want to taste a bit.

Assume your laptop/PC is UEFI-capable.

---

First thing as breathe air is to read [Installation guide](https://wiki.archlinux.org/index.php/Installation_guide). Read through the guide slowly and carefully.

After that, get an USB and follow [USB flash installation media](https://wiki.archlinux.org/index.php/USB_flash_installation_media). Use `dd` on Linux/MacOS or `Rufus` on Windows.

When booting Archlinux ISO, follow **Installation guide**, step by step.

In step **Connect to the internet**.
Enable wifi with `wifi-menu`.

In step **Partition the disks**.
Use `cfdisk`.
Mount point `/mnt/efi` with `512 MiB`.
Skip swap because use swap file later.

In step **Boot loader**.
Use [GRUB with UEFI systems](https://wiki.archlinux.org/index.php/GRUB#UEFI_systems).

---

After finish **Installation guide**, don't rush to restart, read [General recommendations](https://wiki.archlinux.org/index.php/General_recommendations) to continue.

Always remember to check dependencies when install packages.

In step **System administration**.
Read [Users and groups](https://wiki.archlinux.org/index.php/Users_and_groups):

- Add user with [Zsh](https://wiki.archlinux.org/index.php/Zsh) shell.
- Set password.
- Enable [Sudo](https://wiki.archlinux.org/index.php/Sudo#Using_visudo) access.

In step **Graphical user interface**.
Display server - install [Xorg](https://wiki.archlinux.org/index.php/Xorg).
Desktop environments - install [Xfce](https://wiki.archlinux.org/index.php/Xfce) or [MATE](https://wiki.archlinux.org/index.php/MATE).
Display manager - install [LightDM](https://wiki.archlinux.org/index.php/LightDM) or [xinit](https://wiki.archlinux.org/index.php/Xinit).
User directories - install [XDG user directories](https://wiki.archlinux.org/index.php/XDG_user_directories).
Read [File manager functionality](https://wiki.archlinux.org/index.php/File_manager_functionality).

In step **Multimedia**.
Sound - install [ALSA](https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture), [PulseAudio](https://wiki.archlinux.org/index.php/PulseAudio).

In step **Networking**.
Network configuration - install [NetworkManager](https://wiki.archlinux.org/index.php/NetworkManager).
Clock synchronization - install [systemd-timesyncd](https://wiki.archlinux.org/index.php/Systemd-timesyncd).

In step **Optimization**.
Read [Solid state drive](https://wiki.archlinux.org/index.php/Solid_state_drive).

In step **Appearance**.
Read [Fonts](https://wiki.archlinux.org/index.php/Fonts).

Use swap file - install [systemd-swap](https://wiki.archlinux.org/index.php/Swap#systemd-swap).

---

[Improving performance](https://wiki.archlinux.org/index.php/Improving_performance) is small step inside **Optimization**, but it's big to me.

Read [Watchdogs](https://wiki.archlinux.org/index.php/Improving_performance#Watchdogs).
Read [Staggered spin-up](https://wiki.archlinux.org/index.php/Improving_performance/Boot_process#Staggered_spin-up).
Read [Silent boot](https://wiki.archlinux.org/index.php/Silent_boot).

---

`pacman` is your friend!

[Removing unused packages (orphans)](<https://wiki.archlinux.org/index.php/Pacman/Tips_and_tricks#Removing_unused_packages_(orphans)>).

[The Configuration File, pacman.conf](https://wiki.manjaro.org/index.php?title=Pacman_Overview#The_Configuration_File.2C_pacman.conf).

```sh
sudo pacman -Syu && sudo pacman -Rns $(pacman -Qtdq) || true
```

---

Final step is to read [List of applications](https://wiki.archlinux.org/index.php/List_of_applications). Only read section you need.

---

Remove line across screen when using Plank in Xfce: Settings Manager > Window Manager Tweaks > Compositor > **Uncheck** Show shadows under dock windows.

Center windows in Xfce: Settings Manager > Window Manager Tweaks > Placement > Move slider to full large and **Check** At the center of the screen.

---

This is the end. Future update is coming if I feel something need to be changed or I get boring and change my taste :)

**2020-02-04** Add how to center windows in Xfce.

**2020-02-18** Add MATE and xinit.
