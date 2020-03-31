# Docker

Assume you use Archlinux.

Read [Docker](https://wiki.archlinux.org/index.php/Docker).

Start/enable service:

```sh
systemctl start docker.service

systemctl enable docker.service
```

Add your user to `docker` group:

```sh
sudo usermod -aG docker $USER
```

Delete all images, containers, volumes, and networks that are not associated with a container (dangling):

```sh
docker system prune
```

Read [docker run](https://docs.docker.com/engine/reference/commandline/run/).

| option   | example         | explain                                   |
| -------- | --------------- | ----------------------------------------- |
| `-i`     |                 | Keep STDIN open even if not attached      |
| `--name` |                 |                                           |
| `-p`     | `-p 8080:80`    | Publish container port : host port        |
| `--rm`   |                 |                                           |
| `-t`     |                 | Allocate a pseudo-TTY                     |
| `-v`     | `-v ~/abc:/abc` | Bind host directory : container directory |

Run `ubuntu` image:

```sh
docker run --rm -it ubuntu
```
