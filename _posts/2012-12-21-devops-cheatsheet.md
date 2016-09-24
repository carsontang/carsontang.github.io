---
layout: post
title: "DevOps Cheatsheet"
excerpt: "List of commands used for DevOps"
category: 
tags: []
---

### List all installed packages on Ubuntu or Debina
    dpkg --get-selections

### Install a package with RPM
    rpm -ivh foobar.rpm  # install, verbose, use hash tags to mark progress

### Install a package with Alien
    alien -i foobar.rpm
