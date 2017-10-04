---
layout: post
title: "Immutability in Java"
date: 2017-09-28
tags: java
comments: true
share: true
---

More and more people know how important immutable it is, but be careful of misunderstanding. In Java, you could think Object is just a block of memory with methos. When you declare a variable, this variable is just a memory address, although there is no way to access this directly, that points to a block of memory. You could see there are two things **variable address** and **block of memory**. Most of people talk about immutable, they only mention one of two things. For example, you declare `final` before Java variable, it just means you **could not reassign** new Object or block of memory to this variable. But you still **can MODIFY** this block of memory most of time. Is it immutable? This is not immutable! What is really immutable? You have to unable to reassign new Object to original variable and modify the data inside the Object. That's why Effective Java mentions one way to solve it, defensive copy. But you have to do this for all of data inside Object, even you have nested objects.        