# Prometheus

Docker:

```sh
docker run --rm -p 9090:9090 --name prometheus prom/prometheus

# Custom configuration
docker run --rm -p 9090:9090 -v "$(pwd)"/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml --name prometheus prom/prometheus
```

UI

```txt
localhost:9090
localhost:9090/metrics
```

## Pushing metrics

Docker:

```sh
docker run --rm -p 9091:9091 --name pushgateway prom/pushgateway
```

UI:

```txt
localhost:9091
localhost:9091/metrics
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
