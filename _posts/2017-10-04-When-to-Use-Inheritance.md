---
layout: post
title: "When to Use Inheritance?"
date: 2017-10-04
tags:
    - oop
description:
comments: true
share: true
---

In the beginning, I have to say I am not a expert of OOP and I am prefer FP than OOP. In working hour, I am still work with OOP most time.

When to use inheritance? I thought it would be hard to have accurate answer. But there are some of rules we could think twice before we use inheritance.

What is inheritance? It means subclass has most of capabilities of superclass. In other way, it means there is a concept of **IS-A** in inheritance.

* IS-A vs. HAS-A
    * If we want to use inheritance, we have to make sure there is a relationship of **IS-A**. Or we should use composition which implies **HAS-A**.

* Don't use inheritance for reusing code.
    * When we want to reuse code, we could consider **mixin**.

* Favor composition over inheritance
    * This comes from Effective Java.

* When in doubt leave it out.
    * When we doubt should I use inheritance, we should use composition.
    * This also comes from one of Joshua Bloch's talks.
