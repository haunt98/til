# [tarfile](https://docs.python.org/3/library/tarfile.html)

```python
# Read then extract
with tarfile.open(path_to_tarfile) as tar:
    tar.extractall(path_to_extract)

# Create a gzipped archive from file
with tarfile.open(path_to_archive, "w:gz") as tar:
    tar.add(path_to_file, arcname=filename_inside_archive)
```
