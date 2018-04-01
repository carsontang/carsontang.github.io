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

## How to setup Pycharm with a virtualenv
On the Mac, `Command + ,` or `Pycharm -> Preferences -> Project interpreter -> ~/path/to/.env/bin/python3.6`

## Django Internals
When `python manage.py runserver` is run, `execute_from_command_line` from `django.core.management.ManagementUtility` calls `ManagementUtility#execute`, which takes the subcommand `runserver`. This subcommand is eventually passed to a dictionary that maps strings to callbacks. The `runserver` subcommand is then called. `django.setup` in `django/__init__.py`. Eventually, `django.core.management.commands.runserver#run` is called. This method leads to the start up of a WSGIServer.

When a request hits the server, a RegexURLResolver maps the request's path to one of a list of URLs.

## How does the Django development server know to reload a module?
Django monitors every file and checks if the mtime of the file matches its old mtime. If it doesn't, then it reloads the file.

Django settings is essentially a more complicated Python dictionary.

## Django templates and apps
For every installed app, Django will use its templates.
> Django’s template loader will automatically discover templates and static resources in‐ side the installed apps.


## Mezzanine Internals
`python manage.py runserver` first sets the environment variable, `DJANGO_SETTINGS_MODULE`, to the settings module in the project directory.

{% highlight python %}
{% endhighlight %}
