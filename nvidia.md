## Install Nvidia drivers

Run following commands in a terminal:
```
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
sudo dnf makecache 
sudo dnf install akmod-nvidia
```

## Enable fan control in Gnome
Edit ```/etc/X11/Xwrapper.conf``` and add:
```
allowed_users=anybody
needs_root_rights=yes
```

Make sure the line ```Option         "Coolbits" "4"``` is under the Device section in ```/etc/X11/xorg.conf```. Also I'm not sure if this file is there from the beginning or if you have to generate it with nvidia-settings first.

```
# nvidia-settings: X configuration file generated by nvidia-settings
# nvidia-settings:  version 495.46

Section "ServerLayout"
    Identifier     "Layout0"
    Screen      0  "Screen0" 0 0
    InputDevice    "Keyboard0" "CoreKeyboard"
    InputDevice    "Mouse0" "CorePointer"
    Option         "Xinerama" "0"
EndSection

Section "Files"
EndSection

Section "InputDevice"
    # generated from default
    Identifier     "Mouse0"
    Driver         "mouse"
    Option         "Protocol" "auto"
    Option         "Device" "/dev/input/mice"
    Option         "Emulate3Buttons" "no"
    Option         "ZAxisMapping" "4 5"
EndSection

Section "InputDevice"
    # generated from default
    Identifier     "Keyboard0"
    Driver         "kbd"
EndSection

Section "Monitor"
    # HorizSync source: edid, VertRefresh source: edid
    Identifier     "Monitor0"
    VendorName     "Unknown"
    ModelName      "Microstep MSI MAG271CQR"
    HorizSync       222.0 - 222.0
    VertRefresh     48.0 - 144.0
    Option         "DPMS"
EndSection

Section "Device"
    Identifier     "Device0"
    Driver         "nvidia"
    VendorName     "NVIDIA Corporation"
    BoardName      "NVIDIA GeForce GTX 1070"
    Option         "Coolbits" "4"
EndSection

Section "Screen"
    Identifier     "Screen0"
    Device         "Device0"
    Monitor        "Monitor0"
    DefaultDepth    24
    Option         "Stereo" "0"
    Option         "nvidiaXineramaInfoOrder" "DFP-5"
    Option         "metamodes" "DP-2: 2560x1440_144 +0+0, DP-0: nvidia-auto-select +2560+0"
    Option         "SLI" "Off"
    Option         "MultiGPU" "Off"
    Option         "BaseMosaic" "off"
    SubSection     "Display"
        Depth       24
    EndSubSection
EndSection
```