## OpenRGB

1. Install `openrgb`, then follow [this](https://gitlab.com/CalcProgrammer1/OpenRGB/-/blob/master/Documentation/SMBusAccess.md#linux) guide.

> enabling user access to the i2c devices is not necessary (atleast for me)

- I prefer to disable every device in `OpenRGB > Settings > Supported Devices`, only enable what i need/want

2. save a profile with ur preffered lighting

3. You can now run `openrgb -p <profile>` to set it
   
> You may put that in a hyprland `exec` to autostart
