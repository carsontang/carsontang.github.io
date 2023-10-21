---
layout: post
title: Python Packages and Anaconda
excerpt: how to install Python packages with Anaconda
category: python
tags: [python]
---

* [**Python package**](https://docs.python.org/2/tutorial/modules.html#packages) - Packages are a way of structuring Python’s module namespace by using “dotted module names”. For example, the module name A.B designates a submodule named B in a package named A. Just like the use of modules saves the authors of different modules from having to worry about each other’s global variable names, the use of dotted module names saves the authors of multi-module packages like NumPy or the Python Imaging Library from having to worry about each other’s module names.
* [**Python module**](https://docs.python.org/3/tutorial/modules.html) - A module is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended.
* [**Anaconda channel**](https://conda.io/docs/glossary.html#channels) - The locations of the repositories where conda looks for packages. Channels may point to a Cloud repository or a private location on a remote or local repository that you or your organization created. 

### Anaconda commands
* `conda info` - display Anaconda information related to your computer's setup
* `conda env update -f <filename>` - download any new Python modules specified in the file
* `conda list --export > package-list.txt` – save packages for future use
* `conda create -n myenv --file package-list.txt` – reinstall packages from an export file

### Setting up Mayavi with Python 3.5
* Mayavi works on Python 3 now! Simply follow the instructions below, and the proper dependencies will be installed.
* Download [CarND Term 1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit)
* Add `conda install -c menpo mayavi=4.5.0` to the `environment.yml` file
* Specifically, `mayavi` (version 4.5.0) from the `menpo` channel must be installed. Also install `numpy`.
* All of Mayavi's dependencies will be installed.

### Displaying Mayavi in Jupyter

Tips taken from here: http://docs.enthought.com/mayavi/mayavi/tips.html

Install JavaScript files: `jupyter nbextension install --py mayavi --user`

After installing the JavaScript files, the following instructions are given, but **they don't work with the environment above**. To initialize this nbextension in the browser every time the notebook (or other app) loads:
`jupyter nbextension enable mayavi --user --py`
