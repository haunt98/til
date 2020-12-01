# [OpenSSH](https://www.openssh.com/)

| Distribution | Package                         |
| ------------ | ------------------------------- |
| Arch Linux   | `openssh`                       |
| Ubuntu       | `openssh-client openssh-server` |
| Ubuntu       | `openssh`                       |

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
ssh-keygen -t rsa -b 4096 -C "your@email.com"
```

Start `ssh-agent`:

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
