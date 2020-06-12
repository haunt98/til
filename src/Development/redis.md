# Redis

Docker:

```sh
docker run --rm -p 6379:6379 --name redis redis:alpine
```

## redis-cli

`redis-cli` is included in:

| Distribution | Package        |
| ------------ | -------------- |
| Arch Linux   | `redis`        |
| Ubuntu       | `redis-server` |

Connect:

```sh
redis-cli -h localhost -p 6379
```

### [Commands](https://redis.io/commands)

Get all keys:

```sh
KEYS *
```

Delete all keys:

```sh
FLUSHALL
```
