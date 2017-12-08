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
* You have to be good at design. [[1]]
* Know how low-level things work.

Suddenly, I realized the reasons are not only those. I found out when you work with performance engineering, you always have to conduct benchmark and gather the data from benchmarks. The points are: 

* Data don't lie.
* There is no ambiguity in data.

There is one of my favorite quotes:
> Trust no one, bench everything.

from [sbt-jmh][4] by [Konrad Malawski](https://twitter.com/ktosopl)

However, is it that easy? There is a prerequisite for this. We have to benchmark or measure correctly. It means we have to use right methodologies to do it. For instance, when we benchmark CPU intensive application in Intel CPU, we have to turn off hyper-threading. Or we would get a wasteful result. [Aleksey Shipilëv told about this in one of his talks][5].

Last but not least, anyone is interested in performance engineering. There are stuffs I would suggest to read. 
* [Systems Performance: Enterprise and the Cloud][2] 
* Some of RFCs. For example, [rfc2544][3].
* [Java Microbenchmark Harness: The Lesser of Two Evils][6]

Reference:
1. [Good design usually coincides with good performance][1] by Joshua Bloch
2. [Systems Performance: Enterprise and the Cloud][2] by Brendan Gregg, Netflix Senior Performance Architect
3. [Benchmarking Methodology for Network Interconnect Devices][3]
4. [Java Microbenchmark Harness: The Lesser of Two Evils][6]

    [1]: http://www.cs.bc.edu/~muller/teaching/cs102/s06/lib/pdf/api-design   
    [2]: https://www.amazon.com/Systems-Performance-Enterprise-Brendan-Gregg/dp/0133390098/
    [3]: https://www.ietf.org/rfc/rfc2544.txt
    [4]: https://github.com/ktoso/sbt-jmh
    [5]: https://www.youtube.com/watch?v=VaWgOCDBxYw&t=15m45s
    [6]: https://www.youtube.com/watch?v=VaWgOCDBxYw
