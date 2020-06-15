# [Consul](https://www.consul.io/)

Docker:

```sh
docker run --rm -p 8500:8500 -p 8600:8600/udp --name=consul consul agent -server -ui -bootstrap-expect=1 -client=0.0.0.0
```

UI endpoint:

```txt
localhost:8500
```
