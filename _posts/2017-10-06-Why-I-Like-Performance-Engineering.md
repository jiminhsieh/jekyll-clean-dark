---
layout: post
title: "Why I Like Performance Engineering?"
date: 2017-10-06
tags: 
    - performance
    - own opinion
description: 
comments: true
share: true
---

I always like to know things about performance. In the beginning, I thought it's an interesting thing to know something in depth. The reasons of this is that :
* You have to be good at design. [1]
* Know how low-level things work.

Suddenly, I realized the reasons are not only those. I found out when you work with performance engineering, you always have to see the data from benchmarks. The points are: 

* Data don't lie.
* There is no ambiguity in data.

There is one of my favorite quotes - 
> Trust no one, bench everything.

by [Konrad Malawski](https://twitter.com/ktosopl)

However, is it that easy? There is a prerequisite for this. We have to benchmark or measure correctly. It means we have to use right methodologies to do it. For instance, when we benchmark CPU intensive application in Intel CPU, we have to turn off hyper-threading. Or you would get a wasteful result.

Last but not least, anyone is interested in performance engineering. There are stuffs I would suggest to read. 
* [Systems Performance: Enterprise and the Cloud](https://www.amazon.com/Systems-Performance-Enterprise-Brendan-Gregg/dp/0133390098/) by Brendan Gregg
* Some of RFC. For example, [rfc2544](https://www.ietf.org/rfc/rfc2544.txt)(Benchmarking Methodology for Network Interconnect Devices)

Reference -
[1]: Good design usually coincides with good performance. by Joshua Bloch
