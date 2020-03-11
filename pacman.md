# pacman

Assume you use Archlinux.

Read [pacman](https://wiki.archlinux.org/index.php/pacman).

Read [Mirrors](https://wiki.archlinux.org/index.php/Mirrors).

Uncomment/add options in `/etc/pacman.conf`:

```txt
# Misc options
Color
ILoveCandy
```

Read [Force pacman to refresh the package lists](https://wiki.archlinux.org/index.php/Mirrors#Force_pacman_to_refresh_the_package_lists) and [Removing unused packages (orphans)](<https://wiki.archlinux.org/index.php/Pacman/Tips_and_tricks#Removing_unused_packages_(orphans)>):

```sh
sudo pacman -Syyuu && sudo pacman -Rns $(pacman -Qtdq) || true
```
