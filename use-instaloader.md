# Use Instaloader

[Instaloader](https://instaloader.github.io/) is a tool for download Instagram photos, videos, ...

---

Install Instaloader with Python venv.

Create `argx.txt` file with content, remember to change `username` with your real username:

```txt
--no-video-thumbnails
--no-captions
--no-metadata-json
--fast-update
--login=username
--sessionfile=./session
```

Then run, remeber to change `targetname1`, `targetname2`, ... to your target:

```sh
instaloader +args.txt targetname1 targetname2
```
