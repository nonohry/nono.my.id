---
layout: post
title: How to Install .Deb on Manjaro
date: 2021-11-11 00:00:00 +0800
category: tutorial
thumbnail: /style/image/logo.png
icon: book
---

* content
{:toc}

Install debtap:

```
yay -S debtap
sudo debtap -u
```
Convert .deb packages Into Arch Linux Packages using debtap:
```
debtap packagename.deb
```
install the package in the system:
```
sudo pacman -U package-name
```

Reference:

- [How to Install .Deb](https://forum.manjaro.org/t/how-to-install-deb/34452/2)
