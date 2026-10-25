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

## Tested Environment

This package was tested on real hardware with the following specifications:
- **Device**: HUAWEI MACHD-WXX9 (Version: M1020 / MateBook X Pro 2021)
- **Audio Codec**: Conexant CX11880 (`sof-hda-dsp`)
- **OS**: CachyOS Linux (Kernel: 7.3.0-4-cachyos)

## AI Disclosure

This PKGBUILD package and its accompanying configuration were prepared with the assistance of AI (Google DeepMind Antigravity).

## Disclaimer

This package was developed for **personal use** and is provided **"as is" without warranty of any kind**, either express or implied. Use it at your own risk.
