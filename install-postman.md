# Install Postman

Read [Postman - Installation and updates](https://learning.postman.com/docs/postman/launching-postman/installation-and-updates/).

Assume you use Linux.

## Install manually

[Download](https://www.postman.com/downloads/) and unzip the app to `/opt`.

Edit `~/.local/share/applications/Postman.desktop`:

```txt
[Desktop Entry]
Encoding=UTF-8
Name=Postman
Exec=/opt/Postman/app/Postman %U
Icon=/opt/Postman/app/resources/app/assets/icon.png
Terminal=false
Type=Application
Categories=Development;
```
