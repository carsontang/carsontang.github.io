---
layout: post
title: Node Native Addons
excerpt: There are multiple ways to implement Node Addons with C/C++
category: node
tags: [node, javascript]
---

## Major Native Addon Methods
* V8 - JavaScript runtime created by Google
* ChakraCore - JavaScript runtime created by Microsoft to compete with V8
* NAN - Node Native addon abstraction layer atop V8, to shield users from the underlying V8 changes
* N-API - C abstraction layer that's compatible with both V8 and ChakraCore
* node-addon-api - C++ abstraction layer built atop N-API

## node-addon-api
`Env` - created and passed by Node.js runtime, contains the environment in which request is being run

Use `info.As<>()` to cast to another `Napi::Value` type.

`Value` <- `Object` <- `ArrayBuffer`

`Value` <- `Object` <- `TypedArray` <- `TypedArrayOf`