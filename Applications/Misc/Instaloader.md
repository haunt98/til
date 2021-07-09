# [Instaloader](https://instaloader.github.io/)

Should install Instaloader with Python venv:

```sh
# Activate venv
python3 -m pip install instaloader
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

Download stories:

```txt
--stories
--no-posts
--no-profile-pic
```

Download highlights:

```txt
--highlights
--no-posts
--no-profile-pic
```

Create `targets.txt`

```txt
targetname1
targetname2
```

Example how to run, remember to rename `???` to your actual filename config:

```sh
python3 -m instaloader +args.txt +??? +targets.txt
```
