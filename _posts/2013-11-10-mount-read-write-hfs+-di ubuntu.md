---
layout: post
title:  "Mount Read & Write HFS+ on Ubuntu"
tags: [Ubuntu]
---

These steps Mount Read & Write HFS+ on Ubuntu[^1]

Step 1: Install hfsprogs

```bash
sudo apt install hfsprogs
```

Step 2: Check status of drive

```bash
sudo fsck.hfsplus -f /dev/sdXY
```

Step 3: Unmount device

```bash
sudo umount /media/nono/devicename
```

The last, mount the drive with HFS+ read/write permissions:

```bash
sudo mount -t hfsplus -o force,rw /dev/sdXY /home/nono/foldername
```



Reference:

[^1]:https://askubuntu.com/questions/332315/how-to-read-and-write-hfs-journaled-external-hdd-in-ubuntu-without-access-to-os

