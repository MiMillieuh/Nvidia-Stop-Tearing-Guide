# Nvidia-Stop-Tearing-Guide

A guide to "prevent" tearing on Optimus laptop (nothing here is guaretee to work).

## Some args to limit Nvidia Tearing :

These args can be used on Lutris or on Flatseal for flatpaks. it works also in softwares if you add these lines before.

`DRI_PRIME=pci-0000_01_00_0` 

`__VK_LAYER_NV_optimus=NVIDIA_only`

`__GLX_VENDOR_LIBRARY_NAME=nvidia`

## Gamemode :

You can also add this line to gamemode if you want to use the GPU when gamemode is in use.

`GAMEMODERUNEXEC="env __NV_PRIME_RENDER_OFFLOAD=1 __GLX_VENDOR_LIBRARY_NAME=nvidia __VK_LAYER_NV_optimus=NVIDIA_only"`

## Nvidia modprobe.d :

This might help the driver to be a bit less laggy.

In `/etc/modprobe.d/nvidia-graphics-drivers.conf` add `options nvidia-drm modeset=1`

Then update initramfs :

On some distro : `sudo update-initramfs -u`

On fedora : `sudo dracut --force`

On Silverblue : `rpm-ostree initramfs-etc --force-sync`

## Nvidia Settings :

Go in the Nvidia Settings application

![Capture d’écran du 2022-11-18 23-52-41](https://user-images.githubusercontent.com/52078885/202816433-76da1bf0-676e-443b-810a-e8c0e797e66b.png)

Then go to application profile and click on the + icon :

![Capture d’écran du 2022-11-18 23-52-41](https://user-images.githubusercontent.com/52078885/202816535-3c509d5c-a5a5-4389-85ad-c1cda1ef0201.png)

Select Always applie and new profile

![Capture d’écran du 2022-11-18 23-55-45](https://user-images.githubusercontent.com/52078885/202816689-eefab630-a38b-41ac-a02c-8ceab6acc14d.png)

Add GLSyncToVblank and set it to true

if you have GSYNC also add GLGSYNCAllowed and set it to true.

![Capture d’écran du 2022-11-18 23-53-23](https://user-images.githubusercontent.com/52078885/202816820-09b5edb9-2a3d-4346-a239-9e602543f587.png)

Save everything with the plus and I would recomand to reboot.



 ## And remember :
![85dbb77d926274ca72bc89808f5e38bc](https://user-images.githubusercontent.com/52078885/192109754-be64dfa5-d868-4dce-aadb-ff71b7301289.jpg)
