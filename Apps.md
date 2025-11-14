## OpenRGB

1. Install `openrgb`, then follow [this](https://gitlab.com/CalcProgrammer1/OpenRGB/-/blob/master/Documentation/SMBusAccess.md#linux) guide.

> enabling user access to the i2c devices is not necessary (atleast for me)

- I prefer to disable every device in `OpenRGB > Settings > Supported Devices`, only enable what i need/want

2. save a profile with ur preffered lighting

3. You can now run `openrgb -p <profile>` to set it
   
> You may put that in a hyprland `exec` to autostart

## im-emoji-picker

reference: https://github.com/GaZaTu/im-emoji-picker

1. Install `fcitx5` and `fcitx5-configtool`

2. Autostart `fcitx5`

- autostart via `exec-once` and float `windowrule` for `fcitx5-configtool` already in my dotfiles

3. Update your `/etc/environment` file to include the following snippet:
```
GTK_IM_MODULE=fcitx
QT_IM_MODULE=fcitx
XMODIFIERS=@im=fcitx
```

4. Create the config file: https://github.com/GaZaTu/im-emoji-picker?tab=readme-ov-file#settings-

5. Open `fcitx-configtool` and change the shortcut of I'm Emoji Picker in the Addons tab to whatever you like

- By default, it's `Ctrl`+`Alt`+`.`, in my dotfiles, `Super`+`.`

Restart your pc.

> [!NOTE]
> You might (will) get a notification from fcitx saying to not set `GTK_IM_MODULE` and linking you to a wiki [page](https://fcitx-im.org/wiki/Using_Fcitx_5_on_Wayland#GTK_IM_MODULE)
> <br /><br />
> You could just remove `GTK_IM_MODULE` from `/etc/environment` and all **will** _probably_ work well, however, if you use legacy GTK apps, you may have to add `gtk-im-module` for the respective gtk version (wiki linked above)
