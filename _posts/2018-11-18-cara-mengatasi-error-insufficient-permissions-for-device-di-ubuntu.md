---
classes: wide
title:  "Cara mengatasi error: insufficient permissions for device di Ubuntu"
tags: [Ubuntu]
published: true
---

ADB (Android Debug Bridge) adalah command line tool yang mengkomunikasikan android device dengan komputer. singkatnya ini adalah aplikasi client server. :)

ketika menggunakan adb saya sempat mengalami masalah ketika saya ingin masuk ke recovery mode dengan menggunakan adb, yang terjadi adalah munculnya pesan error sebagai berikut:

```
error: insufficient permissions for device
```

solusi jika muncul pesan seperti diatas sangat sederhana, oh ya, OS yang saya gunakan adalah Ubuntu, mungkin untuk OS yang lain juga kurang lebih sama.
Pertama, kita hentikan adb server dengan mengetikan perintah:

```
adb kill-server
```

Selanjutnya, start adb server dengan ditambahkan perintah sudo untuk mendapatkan akses root privileges dari OS kita, perintahnya sebagai berikut:

```
sudo adb start-server
```

jika Outuput dari perintah diatas adalah sebagai berikut, maka anda telah berhasil mengatasi masalah error: insufficient permissions for device.

![ADB Server](https://4.bp.blogspot.com/-i0w6_7rEYZw/VtZpHi2-qSI/AAAAAAAAA90/cco59bmiZRQ/s320/adbstart-server.png)

satu lagi mungkin anda bisa mencabut dan memasang kembali kabel usb yang terkoneksi ke android dan komputer.