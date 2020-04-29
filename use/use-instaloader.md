# Use Instaloader

[Instaloader](https://instaloader.github.io/) is a tool for download Instagram photos, videos, ...

---

Install Instaloader with Python venv.

Create `args.txt` file with content, remember to change `username` with your real username:

```txt
--login=username
--sessionfile=./session
--no-video-thumbnails
--no-captions
--no-metadata-json
```

For downloading posts, add to `args.txt`:

```txt
--fast-update
```

For downloading only stories, add to `args.txt`:

```txt
--stories
--no-posts
```

For downloading only hightlights, add to `args.txt`:

```txt
--highlights
--no-posts
```

Then run, remeber to change `targetname1`, `targetname2`, ... to your target:

```sh
instaloader +args.txt targetname1 targetname2
```
