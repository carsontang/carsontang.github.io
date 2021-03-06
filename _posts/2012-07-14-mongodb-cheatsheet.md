---
layout: post
title: "MongoDB Cheatsheet"
excerpt: "MongoDB commands cheatsheet"
category: database
tags: [mongo, database]
---

### Show a list of all databases
    > show dbs

### Use the database named "cheatsheet"
    > use cheatsheet

### Delete the database named "cheatsheet"
    > use cheatsheet
    > db.dropDatabase()

### Show a database's collections
    > show collections

### Show number of items in the collection "testcoll"
    > db.testcoll.count()

### Drop the collection "testcoll"
    > db.testcoll.drop()

### Create a new Rails app with Mongo
    $ rails new cool_app --skip-active-record

Add the following to your Gemfile:
{% highlight ruby %}require 'rubygems'
require 'mongo'
source 'http://gemcutter.org'

gem "rails", "3.0.0"
gem "mongo_mapper"
{% endhighlight %}

### Create a model for Posts with Mongo
    $ rails generate scaffold Post message:string --skip-migration --orm mongo_mapper

## Info
- If no database is selected on startup, the default database is `test`.
- Databases and collections are created only when documents are first inserted.