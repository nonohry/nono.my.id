---
classes: wide
title:  "easy_install pip fails on macOS"
tags: [macOS]
published: true
---

This is what I get:

```
(** start console output)

sudo easy_install pip Password:

Searching for pip Reading https://pypi.python.org/simple/pip/

Download error on https://pypi.python.org/simple/pip/: [SSL: TLSV1_ALERT_PROTOCOL_VERSION] tlsv1 alert protocol version (_ssl.c:590) -- Some packages may not be found!

Couldn't find index page for 'pip' (maybe misspelled?)

Scanning index of all packages (this may take a while)

Reading https://pypi.python.org/simple/

Download error on https://pypi.python.org/simple/: [SSL: TLSV1_ALERT_PROTOCOL_VERSION] tlsv1 alert protocol version (_ssl.c:590) -- Some packages may not be found!

No local packages or download links found for pip

error: Could not find suitable distribution for Requirement.parse('pip')**

(** end console output)
```

It is because of the deprecated TLSv1; so you have to install pip in a more round-about way.[^1]

1. You may need to do this as user root:

   ```bash
   curl https://bootstrap.pypa.io/get-pip.py | python
   ```

2. to confirm it is working:

   ```bash
   pip install --upgrade pip
   ```



Reference:

[^1]:https://stackoverflow.com/questions/49825743/easy-install-pip-fails-on-mac-osx

