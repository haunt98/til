# Prometheus

Read [Getting started](https://prometheus.io/docs/prometheus/latest/getting_started/).

Docker:

```sh
docker run -d \
    -p 9090:9090 \
    -v /path/to/config:/etc/prometheus \
    --name prometheus
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
    --name pushgateway
    prom/pushgateway
```

UI:

```txt
localhost:9091
```

To configure the Pushgateway as a target to scrape by Prometheus,
add to Prometheus configuration file:

```yaml
scrape_configs:
  - job_name: "pushgateway"
    honor_labels: true
    static_configs:
      - targets: ["localhost:9091"]
```
