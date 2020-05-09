# Prometheus

Read [Getting started](https://prometheus.io/docs/prometheus/latest/getting_started/).

Docker:

```sh
docker run -d \
    -p 9090:9090 \
    -v /path/to/config:/etc/prometheus \
    prom/prometheus
```

UI:

```txt
localhost:9090
```

Metrics:

```txt
localhost:9090/metrics
```

## Pushing metrics

Read [Pushing metrics](https://prometheus.io/docs/instrumenting/pushing/)

Docker:

```sh
docker run -d \
    -p 9091:9091 \
    prom/pushgateway
```
