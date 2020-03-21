# Docker

Assume you use Archlinux.

Read [Docker](https://wiki.archlinux.org/index.php/Docker).

After install docker, add your user to `docker` group.

Delete all images, containers, volumes, and networks that are not associated with a container (dangling):

```sh
docker system prune
```
