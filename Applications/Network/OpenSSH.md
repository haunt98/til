# [OpenSSH](https://www.openssh.com/)

| Distribution | Package                         |
| ------------ | ------------------------------- |
| Arch Linux   | `openssh`                       |
| Ubuntu       | `openssh-client openssh-server` |

Edit `~/.ssh/config`:

```txt
Host myserver
    Hostname server-address
    User user
    Port port
    IdentityFile /path/to/private/key
```

Connect:

```sh
ssh -p port user@server-address
ssh myserver
```

## SSH key

Remove keys in `known_hosts`:

```sh
# Remove all
rm -rf ~/.ssh/known_hosts

# Remove only 1
ssh-keygen -R remote_host
```

### Copy local key to server

Generate key:

```sh
ssh-keygen -t ed25519 -C "your@email.com"
```

Start `ssh-agent`:

```sh
eval "$(ssh-agent -s)"
```

Add key:

```sh
ssh-add ~/.ssh/id_ed25519
```

Copying public key to server:

Linux:

```sh
ssh-copy-id -i ~/.ssh/id_ed25519.pub user@server-address
```

Windows:

```powershell
cat ~/.ssh/id_ed25519.pub | ssh user@server-address "cat >> ~/.ssh/authorized_keys"
```

#### ssh-add

Confirm key has been added:

```sh
ssh-add -l
```

Delete all keys:

```sh
ssh-add -D
```
