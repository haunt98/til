# [argparse](https://docs.python.org/3/library/argparse.html)

```python
import argparse

parser = argparse.ArgumentParser()

# Positional arguments

# python main.py unicorn
parser.add_argument("project", help="project name")

# Optional arguments

# Require following value
# python main.py unicorn -u anon
parser.add_argument("-u", "--user", help="user name")

# Not require following value
# python main.py unicorn -u anon -p
parser.add_argument("-p", "--patch", help="enable patch time", action="store_true")

args = parser.parse_args()

project = args.project
user = args.user
patch = bool(args.patch)
```
