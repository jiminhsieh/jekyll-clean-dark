---
layout: post
title: "Authentication in Spring Security"
date: 2017-11-12
tags: java spring
description:
comments: true
share: true
---

Recently, I need to deal one issue related Spring Security 3.2.x. In the current use case, `Authentication` will be shared in concurrent environment.

After some of studying, I found some of things I didn't know before. 

1. How Spring Security store Authentication
2. ThreadLocal

Spring Security will store Authentication in `SecurityContextHolderStrategy strategy` which is in the class of `SecurityContextHolder`.

`SecurityContextHolderStrategy` is just an interface. There are three implementation. Each of them means different strategy of storing `Authentication`.

Here are 3 strategies:

1. Global
2. InheritableThreadLocal
    * When you create InheritableThreadLocal in parent thread, all of his child threads will see the same value as parent thread.
3. ThreadLocal
    * Each thread will own his value.

By default, Spring Security will use ThreadLocal. Or you could set other strategies when application initializes Spring container. For general web container like Tomcat or Jetty, it's not a big issue. Since Tomcat and Jetty will have handle request to response in the same thread. 

However, I am curious about does Spring Security work for WildFly. How WildFly handle HTTP request is really different from Tomcat. WildFly uses IO threads to handle each of request then dispatch to worker threads. It means one request could be cross to different threads. 
