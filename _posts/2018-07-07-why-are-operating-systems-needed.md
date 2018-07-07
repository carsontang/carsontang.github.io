---
layout: post
title: Why are operating systems needed?
excerpt: Reasons why computers run an OS.
category: os
tags: [os]
---

Imagine computers without operating systems. An application could link in libraries to accomplish its goals. For example, a PC game would need to link in libraries to talk to the CPU, GPU, memory, etc. The PC game developer could choose to hog all the computer's resources, and there would be nothing to force the game to share those resources with other processes and applications. An OS abstracts away all the resources - it's an API for the computer's resources. Behind the API is logic that controls when and for how long an application can obtain the computer's resources.