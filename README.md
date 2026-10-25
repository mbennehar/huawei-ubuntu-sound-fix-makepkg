# huawei-ubuntu-sound-fix-makepkg

Arch Linux PKGBUILD package for [Smoren/huawei-ubuntu-sound-fix](https://github.com/Smoren/huawei-ubuntu-sound-fix).

## Installation

Build and install using `makepkg`:

```bash
makepkg -si
```

This clones the upstream repository into `src/` and runs `install.sh` during post-installation, copying the daemon script and systemd service and starting `huawei-soundcard-headphones-monitor.service`.

## Uninstallation

Uninstall using `pacman`:

```bash
sudo pacman -R huawei-ubuntu-sound-fix
```

The package automatically runs upstream `uninstall.sh` upon removal, stopping and disabling the service and cleaning up the installed files.
