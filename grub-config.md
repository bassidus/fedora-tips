## Enable grub menu and remember last choice

Edit ```/etc/default/grub``` and add the following lines:
```
GRUB_TIMEOUT=2
GRUB_DISTRIBUTOR="$(sed 's, release .*$,,g' /etc/system-release)"
GRUB_DEFAULT=saved
GRUB_SAVEDEFAULT=true
GRUB_DISABLE_SUBMENU=true
GRUB_TERMINAL_OUTPUT="console"
GRUB_CMDLINE_LINUX="rd.driver.blacklist=nouveau modprobe.blacklist=nouveau nvidia-drm.modeset=1 rhg>
GRUB_DISABLE_RECOVERY="true"
GRUB_ENABLE_BLSCFG=true
GRUB_TIMEOUT_STYLE=menu
```
Run ```sudo grub2-mkconfig -o /etc/grub2-efi.cfg```

All done!