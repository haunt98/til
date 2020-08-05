# [inkscape](https://gitlab.com/inkscape/inkscape)

Convert `.svg` to `.png`:

```sh
# version < 1.0
inkscape -z -w 1024 -h 1024 input.svg -e output.png

# version >= 1.0
inkscape -w 1024 -h 1024 input.svg --export-filename output.png
```
