# alpine-setup
icons:
```
apk add adwaita-icon-theme gnome-brave-icon-theme gnome-icon-theme
```
use gnome-brave

fonts:
```
apk add ttf-freefont ttf-droid-nonlatin
```

file manager:
```
apk add pcmanfm
```

mtp:
```
apk add simple-mtpfs android-udev-rules
```
then to make your non root user to be able to mount, add this to `/usr/lib/udev/rules.d/51-android.rules`
this is for samsung galaxy, change OWNER, idVendor, idProduct according yours. If you don't know idVendor and idProduct, install `usbutils` and check it with `lsusb`.
```
SUBSYSTEM=="usb", ATTR{idVendor}=="04e8", ATTR{idProduct}=="6860", OWNER="ruivlea"
```
enable fuse
```
apk add fuse fuse-openrc && rc-update add fuse && rc-service fuse start
```
