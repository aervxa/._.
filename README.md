# ._. **⚠️ WIP ⚠️**

A simple guide to setup a basic setup for arch linux while learning along the way! (without messing up). actually setting ur arch up, not copying  "dotfiles" or running pre-configured install scripts.

> clicking the links for further understanding is recommended, but if it confuses you, skip it! seriously, it will only confuse you more. (then just watch some beginner stuff on yt, works wonders)

Desktop environments targetted: Hyprland, with KDE/minimal as a safe fallback.
> Having less total packages in ur PC would not make your PC that much faster, keep KDE as a fallback until you feel comfortable blindfolded /s (s is for sarcasm btw)

> ### ⚠️ a basic understanding of what is what is needed since this guide is not written that well _yet_.

## Installation of Arch via `archinstall`

> ('ch' in 'arch' is pronounced as in 'ch' in 'change', not 'ark')

**the following options are required:**
- fs: btrfs (default structure + compression)
> fs is udner disk config (manual partition > select disk > suggest layout > btrfs)
- hostname: give ur pc a cool name
- authentication: root + user (sudo)
- network: copy iso

**it is also recommended to set the following, but it is not required:**
- mirrors: select your region
- timezone: select your timezone

> ### ⚠️ It is important you leave everything else as-is

Once the installation completes successfully, reboot into your newly installed system..

## Installation of KDE Plasma (basic "usability" setup)

Login to your system with the user you created (username + password)

> Minimal KDE is recommended if you plan to use kde as only a fallback (and use hyprland as ur main maybe)

Install KDE in either of these two ways:

<details>
<summary>For the minimal KDE: (recommended)</summary>

base: [sddm](https://wiki.archlinux.org/title/SDDM) (login manager), [plasma](https://wiki.archlinux.org/title/KDE#:~:text=Alternatively%2C%20for%20a%20more%20minimal%20Plasma%20installation%2C%20install%20the%20plasma-desktop%20package.) (desktop environment), and [kitty](https://wiki.archlinux.org/title/Kitty) (terminal emulator)
```bash
sudo pacman -S sddm plasma-desktop kitty
```
> it will ask you to pick a package for jack, pick `pipewire-jack`, and pick `ffmpeg` for the media backend

> to enable the login manager, you will have to run (will take effect after reboot):
> ```bash
> sudo systemctl enable sddm
> ```

utils: [bluez](https://wiki.archlinux.org/title/Bluetooth) (bluetooth), [pipewire-pulse](https://wiki.archlinux.org/title/PipeWire#PulseAudio_clients) (bt audio), [plasma-pa](https://wiki.archlinux.org/title/KDE#Sound_applet_in_the_system_tray) + [bluedevil](https://wiki.archlinux.org/title/Bluetooth#Graphical#:~:text=Bluedevil) (kde plasma applet support for audio and bluetooth respectively)
```bash
sudo pacman -S bluez pipewire-pulse plasma-pa bluedevil
```

> to enable bluetooth, you will have to run (will take effect after reboot):
> ```bash
> sudo systemctl enable sddm
> ```

</details>

<details>
<summary>For the whole KDE experience:</summary>

the one universal package [`plasma`](https://wiki.archlinux.org/title/KDE#:~:text=the%20plasma%20group.) for the whole OOBE:
```bash
sudo pacman -S plasma
```
</details>

Now reboot.
