## Linux driver for the Xbox One wireless dongle

xow is a Linux user mode driver for the Xbox One wireless dongle.
It communicates with the dongle via libusb and provides joystick input through the uinput kernel module.
The input mapping is based on existing kernel drivers like xpad.

Installation Instructions

Installation:
```
dnf copr enable sentry/xow
dnf install xow
```
Removal:
```
dnf copr disable sentry/xow
dnf remove xow xow-firmware lpf-xow-firmware
```

Links
* https://github.com/medusalix/xow
* https://copr.fedorainfracloud.org/coprs/sentry/xow/