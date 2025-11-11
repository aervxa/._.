# "Ideal" setup of your KDE

By now, you should know that 'installing' something would mean using `pacman` for it, unless specified either. Usually 'ᴬᵁᴿ' would be specified for the Arch User Repository.

> the AUR is where everything that if not "official" by the Arch team goes, hence the name, "User" repository. Practicing caution when installing for the AUR is adviced.

> ### I won't list the whole installations of each thing i used, but what i will do is list it, and what it does.
> If i link a github repo, make sure to follow it's installation guide completely, otherwise the package itself would be enough for the functionality.

## Installing the AUR helper installer

the steps to installing from the AUR is to manually build the repository, but fear not, we have helpers.

Installation of `yay` (or you could follow the [official installation](https://github.com/Jguer/yay?tab=readme-ov-file#installation)):

1. git clone https://www.aur.archlinux.org/yay.git
2. cd yay
3. makepkg -si

## "Aesthetic"/"Base" additions

The ones that don't need it's own section:

- `ffmpegthumbs` (thumbnails for video files in dolphin)
- [`sddm-silent-theme`](https://github.com/uiriansan/SilentSDDM?tab=readme-ov-file#AUR-packages-for-arch)ᴬᵁᴿ (sddm theme)
- `gwenview` (image viewer)
- `kcalc` (calculator)
- `kclock` (clock app for alarms and so on)
- `kwrite` (i need a notepad like thing to type on)

Things that include it's .config but doesn't need it's own section:

> If you just installed the package, feel free to overwrite the config files

- `spectacle` ((config)[.config/spectaclerc])
