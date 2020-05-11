# [Instaloader](https://instaloader.github.io/)

Should install Instaloader with Python venv.

Create `args.txt`, remember to change `username` with your real username:

```txt
--login=username
--sessionfile=./session
--no-video-thumbnails
--no-captions
--no-metadata-json
```

Want more custom? Add to `args.txt`.

Downloading posts:

```txt
--fast-update
```

Downloading only stories:

```txt
--stories
--no-posts
```

Downloading only hightlights:

```txt
--highlights
--no-posts
```

Filter posts:

```txt
--post-filter="date_utc <= datetime(2020, 6, 30)"
```

Finally run, remember to change `targetname1`, `targetname2`, ... to your target:

```sh
instaloader +args.txt targetname1 targetname2
```
