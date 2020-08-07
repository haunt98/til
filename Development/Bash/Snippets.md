# Snippets

Loop over files:

```sh
for filename in ./*.png
do
    echo "Processing $filename"
done
```

Basename:

```
# Output is image.png
basename image.png

# Output is image
basename image.png .png
```
