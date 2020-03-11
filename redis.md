# Redis

Assume you use Archlinux.

Read [Redis](https://wiki.archlinux.org/index.php/Redis).

After install `redis`, start service:

```sh
systemctl start redis.service
```

Otherwise use docker:

```sh
docker run -d -p 6379:6379 --name redis redis:alpine
```

## redis-cli

Connect:

```sh
redis-cli -h localhost -p 6379
```

### After connect

Get all keys:

```sh
KEYS *
```

Delete all keys:

```sh
FLUSHALL
```

Read [Commands](https://redis.io/commands).
