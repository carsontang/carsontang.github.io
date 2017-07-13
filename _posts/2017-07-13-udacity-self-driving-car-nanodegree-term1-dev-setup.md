---
layout: post
title: Udacity Self Driving Car Nanodegree Term 1 Dev Setup
excerpt: Notes on installing software for Udacity's SDCND Term 1.
category: machine learning
tags: [machine learning]
---

{% highlight bash %}
mkdir udacity_sdc_nd
cd udacity_sdc_nd
sudo pip install virtualenv      # This may already be installed
python3 -m venv .env             # Create a virtual environment (python3)
source .env/bin/activate         # Activate the virtual environment
pip install -r requirements.txt
{% endhighlight %}

See the [CarND Term 1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit) if you want to use Udacity's official setup.