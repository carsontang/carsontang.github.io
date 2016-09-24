---
layout: post
title: The Magic of the Java G1 Garbage Collector
excerpt: "Using the Java G1 Garbage Collector, it's possible to claim back thousands of physical hosts in your web service setup."
category: Java
tags: [Java, gc]
---

Suppose you have a shortage of physical hosts, and you'd like to reclaim a lot of them to use for other web services your company is supporting. Using [YourKit](https://www.yourkit.com/), a Java profiler, if you detect that a lot of your Java objects live for a relatively short amount of time (~0.5s), 