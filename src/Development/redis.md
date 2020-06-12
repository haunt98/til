# [Redis](https://redis.io/)

Docker:

```sh
docker run --rm -p 6379:6379 --name redis redis:alpine
```

## Command-line interface

### redis-cli

| Distribution | Package        |
| ------------ | -------------- |
| Arch Linux   | `redis`        |
| Ubuntu       | `redis-server` |
| Homebrew     | `redis`        |

Connect:

```sh
redis-cli -h localhost -p 6379
```

### [Redli](https://github.com/IBM-Cloud/redli)

Connect:

```sh
redli -h localhost -p 6379
```

### Commands

Get all keys:

```redis
keys *
```

Delete all keys:

```redis
flushall
```

Get/Set/Delete key:

```redis
get mykey
set mykey myvalue
del mykey
```
