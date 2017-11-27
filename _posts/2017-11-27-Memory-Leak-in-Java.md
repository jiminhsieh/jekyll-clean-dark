---
layout: post
title: "Memory Leak in Java"
date: 2017-11-27
tags: java
description:
comments: true
share: true
---

A lot of people think there is no memory leak in Java because Garbage Collection. Some of them don'e even know there is possibility to memory leak.

In C/C++, it means you don't `free` the memory what you `malloc`. But what is mean of memory leak in Java. It means garbage collector doesn't know garbage object you don't want to use anymore. In other word, garbage object is still been hold from other object.

For example, this is what mentioned in [Effective Java, 2nd](http://www.informit.com/store/effective-java-9780321356680).

{% highlight java %}
public class Stack {
  private Object[] elements;
  private int size = 0;
  private static final int DEFAULT_INITIAL_CAPACITY = 16;

  public Stack() {
    elements = new Object[DEFAULT_INITIAL_CAPACITY];
  }

  public void push(Object e) {
    ensureCapacity();
    elements[size++] = e;
  }

  public Object pop() {
    if (size == 0)
      throw new EmptyStackException();
    return elements[--size];
  }
  
  private void ensureCapacity() {
    if (elements.length == size)
      elements = Arrays.copyOf(elements, 2 * size + 1);
  }
}
{% endhighlight %}

In this snippet of source code, `pop()` will cause *memory leak*. This is because of the element you pop will keep in the array of `elements`. You have to null original location of array. 
Like this: 
{% highlight java %}
    public Object pop() {
        if (size == 0)
          throw new EmptyStackException();
        Object result = elements[--size];
        elements[size] = null;
        return result;
    }
{% endhighlight %}

Other examples are you don't close SQL Statements, SQL ResultSet, and SQL Connection or other types of connection correctly.
