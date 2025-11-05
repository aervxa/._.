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

## NOTE: To keep the main README short, the kde installation and hyprland installation will be in seperate files:

KDE Plasma setup's [README](KDE.md)

Hyprland setup's [README]() | ⚠️ WIP ⚠️
