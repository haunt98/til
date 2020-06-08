# venv

Python venv is Python Virtual Environment.
Why do we need to use Python venv?
Because we don't want to mess up with Python packages which are stored in different location: system directories, user directories, ...

Assume you use Python 3 and Linux.

---

Python venv stores everything in a local directory.

Inside chosen directory, run:

```sh
python -m venv venv
```

Now you can use venv with:

```sh
source ./venv/bin/activate
```
