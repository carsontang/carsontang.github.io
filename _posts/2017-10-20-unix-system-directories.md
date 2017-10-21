---
layout: post
title: Unix System Directories
excerpt: description of well-known directories
category: macosx
tags: [macosx]
---

* `/bin`: Unix binaries. This is where the common UNIX commands (for example, `ls`, `rm`, `mv`, `df`) are.
* `/sbin`: System binaries. These are binaries used for system administration, such as file-system management, network configuration, and so on.
* `/usr`: The User directory. This is not meant for users, but is more like Windows’ program files in that third-party software can install here.
* `/usr`: Contains in it `bin`, `sbin`, and `lib`. `/usr/lib` is used for shared objects (think, Windows DLLs and \windows\system32). This directory also contains the include/ subdirectory, where all the standard C headers are.
* `/etc`: Et Cetera. A directory containing most of the system configuration files; for example, the password file (`/etc/passwd`). In OS X, this is a symbolic link to `/private/etc`.
* `/dev`: BSD device files. These are special files that represent hardware devices on the system (character and block devices).
* `/tmp`: Temporary directory. The only directory in the system that is world-writable (permissions: rwxrwxrwx). In OS X, this is a symbolic link to `/private/tmp`.
* `/var`: Various. A directory for log files, mail store, print spool, and other data. In OS X, this is a symbolic link to `/private/var`.