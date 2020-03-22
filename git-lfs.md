# Git LFS

Read [Git Large File Storage](https://git-lfs.github.com/).

After install, run this once:

```sh
git lfs install
```

Select the file types for Git LFS to manage:

```sh
git lfs track "*.pdf"
```

Make sure `.gitattributes` is tracked:

```sh
git add .gitattributes
```

From now on, clone repository will call Git LFS if possible.
