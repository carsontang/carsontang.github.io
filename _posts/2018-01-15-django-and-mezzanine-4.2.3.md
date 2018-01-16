---
layout: post
title: Customize Themes with Django 1.10.8 with Mezzanine 4.2.3
excerpt: Step-by-step guide to customizing the CSS in Mezzanine with Django.
category: python
tags: [python]
---

## How to set up custom CSS in Mezzanine
{% highlight bash %}
$ mkdir myproject
$ cd myproject
$ virtualenv -p python3 .env
$ source .env/bin/activate
$ echo "mezzanine==4.2.3" > requirements.txt
$ pip install -r requirements.txt
$ mezzanine-project myproject
$ cd myproject
$ python manage.py createdb
$ python manage.py collecttemplates -t base.html # just copy the base template over
# you should see a templates directory now
$ mkdir -p static/css # this should be done in the myproject/ directory
$ curl https://bootswatch.com/4/solar/bootstrap.min.css -o "static/css/bootstrap.solar.min.css"
# Go to templates/base.html and add a link to the stylesheet above
{% endhighlight %}
