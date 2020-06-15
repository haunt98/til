# Docker

| Distribution | Package                                               |
| ------------ | ----------------------------------------------------- |
| Arch Linux   | `docker`                                              |
| Ubuntu       | [See](https://docs.docker.com/engine/install/ubuntu/) |

Enable and start service:

```sh
systemctl enable --now docker.service
```

Add your user to `docker` group:

```sh
sudo usermod -aG docker $USER
```

## Command-line

Remove unused data:

```sh
docker system prune

docker system prune -a
```

Docker run options:

| option                | example                  | explain                                 |
| --------------------- | ------------------------ | --------------------------------------- |
| `--detach`, `-d`      |                          | Run container in background             |
| `--env`, `-e`         | `-e PLATFORM=linux`      | Set environment variables               |
| `--interactive`, `-i` |                          | Keep STDIN open                         |
| `--name`              |                          |                                         |
| `--publish`, `-p`     | `-p 8080:80`             | Publish container port:host port        |
| `--rm`                |                          | Remove container when exit              |
| `--tty`, `-t`         |                          | Allocate a pseudo-TTY                   |
| `--volume`, `-v`      | `-v "$(pwd)"/data:/data` | Bind host directory:container directory |