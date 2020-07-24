# [subprocess](https://docs.python.org/3/library/subprocess.html)

```python
import subprocess

subprocess.run(["ls", "-a"])

# Stop when run error
subprocess.run(["exit 1"], check=True)
```
