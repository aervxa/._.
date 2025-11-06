# Installation of KDE Plasma

Login to your system with the user you created (username + password)

> **Minimal KDE is recommended**, you could always add whatever you need later on
> if you want the whole OOBE and the whole plasma package, you can install [`plasma`](https://wiki.archlinux.org/title/KDE#:~:text=the%20plasma%20group.)

Install KDE step by step:

**base:**

1. Install [sddm](https://wiki.archlinux.org/title/SDDM) (login manager), [plasma](https://wiki.archlinux.org/title/KDE#:~:text=Alternatively%2C%20for%20a%20more%20minimal%20Plasma%20installation%2C%20install%20the%20plasma-desktop%20package.) (desktop environment), and [kitty](https://wiki.archlinux.org/title/Kitty) (terminal emulator)
```bash
sudo pacman -S sddm plasma-desktop kitty
```
> if the installer asks you to pick a package for "jack", pick `pipewire-jack`, and pick `ffmpeg` for the "media backend"

2. Enable `sddm` (will take effect after reboot):
```bash
sudo systemctl enable sddm
```

**utils:**

1. Install [bluez](https://wiki.archlinux.org/title/Bluetooth) (bluetooth), [pipewire-pulse](https://wiki.archlinux.org/title/PipeWire#PulseAudio_clients) (bt audio), [plasma-pa](https://wiki.archlinux.org/title/KDE#Sound_applet_in_the_system_tray) + [bluedevil](https://wiki.archlinux.org/title/Bluetooth#Graphical#:~:text=Bluedevil) (kde plasma applet support for audio and bluetooth respectively)
```bash
sudo pacman -S bluez pipewire-pulse plasma-pa bluedevil
```

2. Enable bluetooth (will take effect after reboot):
```bash
sudo systemctl enable bluetooth
```

**network widget:** (optional but recommended, network will still work without this)

1. Install [`networkmanager`](https://wiki.archlinux.org/title/NetworkManager) (network manager):
```bash
sudo pacman -S network-manager
```

2. Enable `networkmanager` (will take effect after reboot):
```bash
sudo systemctl enable NetworkManager
```

3. Install `plasma-nm` (plasma widget for `networkmanager`):
```bash
sudo pacman -S plasma-nm
```

> `plasma-nm` would automatically install and enable `networkmanager` if it's not already installed, but we are trying to setup most of the base on our own, so that if we decide to remove plasma later, crucial components won't go along with it (e.g. Hyprland setup using `networkmanager`)

> steps 4 and 5 is for changing the default wifi backend (_opinionated-ly recommended_), if you're using cable, you may skip this (_steps are still opinionated-ly recommended_)

4. Set the backend to `iwd` (`networkmanager` comes with it's default backend `wa_supplicant`, `iwd` is arch's default, so it's more seamless to just keep using that):
```bash
sudo bash -c 'printf "[device]\nwifi.backend=iwd" > /etc/NetworkManager/conf.d/wifi_backend.conf'
```

5. Disable the `iwd` "standalone" service (will take effect after reboot):
```bash
sudo systemctl disable iwd
```

### Now reboot. Happy booting!!


After rebooting, you may opt in to install these additionals:

**essential apps:** Install firefox (or any other browser), dolphin (file explorer)
```bash
sudo pacman -S firefox dolphin
```

**kde settings:** Install [kde-gtk-config](https://wiki.archlinux.org/title/GTK#:~:text=kde-gtk-config) (GTK theming), kscreen (display settings)
```bash
sudo pacman -S kde-gtk-config kscreen
```
