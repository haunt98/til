# [inkscape](https://gitlab.com/inkscape/inkscape)

| Distribution | Package    |
| ------------ | ---------- |
| Arch Linux   | `inkscape` |
| Ubuntu       | `inkscape` |
| Fedora       | `inkscape` |

Convert `.svg` to `.png`:

```sh
# version < 1.0
inkscape -z input.svg -e output.png

# version >= 1.0
inkscape input.svg --export-filename output.png
```
