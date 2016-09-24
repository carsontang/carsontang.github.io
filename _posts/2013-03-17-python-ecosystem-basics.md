---
layout: post
title: "Python Ecosystem Basics"
excerpt: "Learn about site-packages, Python eggs, and virtualenvwrapper."
category: "Python"
tags: ["Python"]
---

### Installing a Python module
    $ tar -xvzf foo-1.0.tar.gz
    $ cd foo-1.0
    $ python setup.py install

### site-packages
Directory where all Python libraries are installed

### What is a Python egg?
A Python egg is analogous to a Java jar file. It's essentially a zip file
with metadata files renamed as an egg file.

### virtualenvwrapper commands
    $ mkvirtualenv -p python2.7 myapp
    $ lsvirtualenv # list all virtual environments
    $ workon myapp
    $ deactivate

### Install yolk to view packages easily
    $ pip install yolk
    $ yolk -l