# [MinIO](https://min.io/)

Docker:

```sh
docker run --rm -p 9000:9000 --name minio minio/minio server /data

# Persistent storage
docker run --rm -p 9000:9000 -v "$(pwd)"/minio/data:/data --name minio minio/minio server /data
```

UI endpoint, with default credentials `minioadmin:minioadmin`:

```txt
localhost:9000
```
