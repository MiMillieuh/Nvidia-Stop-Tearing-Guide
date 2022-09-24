# Nvidia-Stop-Tearing-Guide

A guide to "prevent" tearing on Optimus laptop (nothing here is guaretee to work).

## Some args to limit Nvidia Tearing :

These args can be used on Lutris or on Flatseal for flatpaks. it works also in softwares if you add these lines before.

`DRI_PRIME=pci-0000_01_00_0` 

`__VK_LAYER_NV_optimus=NVIDIA_only`

`__GLX_VENDOR_LIBRARY_NAME=nvidia`

## Nvidia modprobe.d

This might help the driver to be a bit less laggy.

In `/etc/modprobe.d/nvidia-graphics-drivers.conf` add options `nvidia-drm modeset=1`

Then update initramfs :

On some distro : `sudo update-initramfs -u`

On Silverblue : `rpm-ostree initramfs-etc --force-sync`

 ## And remember :
![85dbb77d926274ca72bc89808f5e38bc](https://user-images.githubusercontent.com/52078885/192109754-be64dfa5-d868-4dce-aadb-ff71b7301289.jpg)
