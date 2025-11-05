 # **⚠️ WIP ⚠️** Set up your very own arch setup!

A simple guide to setup a minimal setup for arch linux while learning along the way! (without messing up). you will actually setup ur arch, not copy  "dotfiles" or run pre-configured install scripts.

Desktop environments targetted: Hyprland, with KDE/minimal as a safe fallback.

> Having less total packages in ur PC would not make your PC that much faster, keep KDE as a fallback until you feel comfortable blindfolded

### ⚠️ a basic understanding of what is what is needed.

# Overview

1. Firstly, Arch Linux will be installed.
2. Second, we will install KDE Plasma as a safe base for you to start your journey, optionally we will also rice KDE
3. If feeling more adventurous, we will also install Hyprland, customize, and rice it (it is recommended to not skip step 2 even if you want _just_ Hyprland)

# 1. Installation of Arch via `archinstall`

### ⚠️ It is important you leave everything else as-is
> If you do know what you're doing, you could customize this as you wish.

**the following options are required:**
- fs: _btrfs_ (default structure + compression)
> fs is under disk config (manual partition > select disk > suggest layout > btrfs)
- hostname: _give ur pc a cool name_
- authentication: _root + user_ (sudo)
- network: _copy iso_

**it is also recommended to set the following, but it is not required:**
- mirrors: _select your region_
- timezone: _select your timezone_

Once the installation completes successfully, reboot into your newly installed system..

## Installation of KDE Plasma (basic "usability" setup)

Login to your system with the user you created (username + password)

> Minimal KDE is recommended if you plan to use kde as only a fallback (and use hyprland as ur main maybe)
if you want the whole OOBE and the whole plasma package, you can install [`plasma`](https://wiki.archlinux.org/title/KDE#:~:text=the%20plasma%20group.)

Install KDE step by step:

**base:**

1. Install [sddm](https://wiki.archlinux.org/title/SDDM) (login manager), [plasma](https://wiki.archlinux.org/title/KDE#:~:text=Alternatively%2C%20for%20a%20more%20minimal%20Plasma%20installation%2C%20install%20the%20plasma-desktop%20package.) (desktop environment), and [kitty](https://wiki.archlinux.org/title/Kitty) (terminal emulator)
```bash
sudo pacman -S sddm plasma-desktop kitty
```
> `plasma-desktop` will ask you to pick a package for "jack", pick `pipewire-jack`, and pick `ffmpeg` for the "media backend"

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

> `plasma-nm` would automatically install and enable `networkmanager` if it's not already installed, but we are trying to setup most of the things on our own, so that we can later switch out `plasma-nm` with anything else if we decide to switch DEs (e.g. Hyprland setup on top of this)

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
