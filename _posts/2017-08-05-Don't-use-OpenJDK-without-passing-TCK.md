---
layout: post
title: "Don't use OpenJDK without passing TCK."
date: 2017-08-05
tags: jvm java scala
description: 
comments: true
share: true
---

## Where is OpenJDK?

If you are using Linux as developing OS, this's not a big deal. You always get OpenJDK from repository. But ***what if you are using Win or macOS***, you won't get built in OpenJDK. If you are doing some search on the Internet, you may find out this unofficial [built](https://github.com/ojdkbuild/ojdkbuild) for each OS. However, looking carefully what README.md they wrote, they don't response any question about the [TCK](https://en.wikipedia.org/wiki/Technology_Compatibility_Kit) which is like JDK's unit testing. So no one would knows did they test their built. Do you want to use software that you don't know test or not? I don't have that courage to use it.

## Where is OpenJDK for Win and macOS?

* macOS
    * [Azul Zulu](http://www.azul.com/downloads/zulu/zulu-mac/)

* Win
    * [RedHat](https://developers.redhat.com/products/openjdk)
    * [Azul Zulu](http://www.azul.com/downloads/zulu/zulu-windows/)

## In the end

You could safely use OpenJDK from Azul System and RedHat which would be test before it release.
