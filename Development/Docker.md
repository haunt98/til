# Docker

| Distribution | Package                                               |
| ------------ | ----------------------------------------------------- |
| Arch Linux   | `docker docker-compose`                               |
| Debian       | [See](https://docs.docker.com/engine/install/debian/) |
| Ubuntu       | [See](https://docs.docker.com/engine/install/ubuntu/) |
| Fedor        | [See](https://docs.docker.com/engine/install/fedora/) |

Enable and start service:

```sh
systemctl enable --now docker.service
```

Add your user to `docker` group:

```sh
sudo usermod -aG docker $USER
```

## Commands

Remove unused data:

```sh
docker system prune --volumes

docker system prune --volumes -a
```

Inside container:

```sh
docker exec -it container_name /bin/bash
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

## Docker Compose

Update images:

```sh
docker-compose pull
```

Start:

```sh
docker-compose up

# Detach
docker-compose up -d
```

Stops:

```sh
docker-compose down
```
