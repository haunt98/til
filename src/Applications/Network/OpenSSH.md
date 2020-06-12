# [OpenSSH](https://www.openssh.com/)

| Distribution | Package   |
| ------------ | --------- |
| Arch Linux   | `openssh` |
| Ubuntu       | `openssh` |
| Homebrew     | `openssh` |

Edit `~/.ssh/config`:

```txt
Host myserver
    Hostname        server-address
    User            user
    Port            port
    IdentityFile    /path/to/private/key
```

Connect:

```sh
ssh -p port user@server-address
ssh myserver
```

## SSH key

Generate key:

```sh
ssh-keygen -t rsa -b 4096 -C "your@email.com"
```

Start:

```sh
eval "$(ssh-agent -s)"
```

Add key:

```sh
ssh-add ~/.ssh/id_rsa
```

Confirm key has been added:

```sh
ssh-add -l
```

Copying public key to server:

```sh
ssh-copy-id -i ~/.ssh/id_rsa.pub user@server-address
```
