---
layout      : post
author      : Nono
title       : Install Virtualbox on Manjaro Linux
description : Install Virtualbox on Manjaro Linux
tags        : [Linux]
---

To install VirtualBox, you need to install the packages virtualbox and linux*-virtualbox-host-modules. The latter must match the version of the kernel you are running.
To install VirtualBox and automatically install the kernel modules for your installed kernels enter the following command in the terminal:
```console
pamac install virtualbox $(pacman -Qsq "^linux" | grep "^linux[0-9]*[-rt]*$" | awk '{print $1"-virtualbox-host-modules"}' ORS=' ') 
```
Once the installation has completed, it will then be necessary to add the VirtualBox Module to your kernel. The easy way is to simply reboot your system. Otherwise, to start using VirtualBox immediately, enter the following command:
```console
sudo vboxreload