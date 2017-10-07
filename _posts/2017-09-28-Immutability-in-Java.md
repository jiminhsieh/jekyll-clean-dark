---
layout: post
title: "Immutability In Java"
date: 2017-09-28
tags: java
comments: true
share: true
---

More and more people know how important immutable it is, but be careful of misunderstanding. In Java, we could think Object is just a block of memory with methods. When we declare a variable, this variable is just a memory address, although there is no way to access this directly, that points to a block of memory. We could see there are two things **variable address** and **block of memory**. Most of people talk about immutable, they only mention one of two things. For example, we declare `final` before Java variable, it just means we **could not reassign** new Object or block of memory to this variable. But we still **can MODIFY** this block of memory most of time. Is it immutable? This is not immutable! What is really immutable? We have to unable to reassign new Object to original variable and modify the data inside the Object. That's why Effective Java mentions one way to solve it, defensive copy. But we have to do this for all of data inside Object, even we have nested objects.        
