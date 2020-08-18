# [Tilix](https://github.com/gnunn1/tilix)

VTE Configuration, add to `~/.bashrc`, `~/.zshrc`:

```sh
if [ $TILIX_ID ] || [ $VTE_VERSION ]; then
    source /etc/profile.d/vte.sh
fi
```
