# [Instaloader](https://instaloader.github.io/)

Should install Instaloader with Python venv:

```sh
# Activate venv
python3 -m pip install instaloader

# Run Instaloader
python3 -m instaloader ...
```

Create `args.txt`, remember to change `username` with your real username:

```txt
--login=username
--sessionfile=./session
--no-video-thumbnails
--no-captions
--no-metadata-json
--fast-update
```

Create `posts.txt`:

```txt
--dirname-pattern={target}/posts
```

Create `stories.txt`:

```txt
--stories
--no-posts
--no-profile-pic
--dirname-pattern={target}/stories
```

Create `hightlights.txt`:

```txt
--highlights
--no-posts
--no-profile-pic
--dirname-pattern={target}/highlights
```

Create `targets.txt`

```txt
targetname1
targetname2
```

Finally, example downloaing posts:

```sh
instaloader +args.txt +posts.txt +targets.txt
```
