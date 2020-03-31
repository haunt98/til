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
