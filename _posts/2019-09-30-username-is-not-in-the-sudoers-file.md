---
title: Username is not in the sudoers file. This incident will be reported
Categories: [Linux]
comments: true
---

ketika mau mengakses sudo su muncul pesan "username is not in the sudoers file. This incident will be reported" maka ketik ini pada terminal
```bash
su
password:<<ketik passwd>>
echo 'username ALL=(ALL) ALL' >> /etc/sudoers
```
contoh:
```bash
su
password:<<ketik passwd>>
echo ‘ryuji ALL=(ALL) ALL’ >> /etc/sudoers
```
