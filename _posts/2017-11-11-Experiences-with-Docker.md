---
layout: post
title: "Experiences with Docker"
date: 2017-11-11
tags: docker
description:
comments: true
share: true
---

I have known Docker for a long time. But in the early year, I used [Vagrant](https://www.vagrantup.com/) heavily and used Docker for fun. This year, I switched from Vagrant to Docker gradually. This is because of I have to use Docker a lot in my working environment. I'm more comfortable with Docker. :D

From my experiences of local development, both of them have their advantage and disadvantage.

* Docker
    * pros
        * It's really fast to start or stop container.
        * It's much lightweight than full virtualization from every aspect.
    * cons
        * To a certain degree, Docker commands are more complexity.
        * It's not easy to set up public IP. Docker heavily relies on internal network.

* Vagrant with VirtualBox
    * pros
        * Vagrant commands are really easy to use. If we need more advance setup, we will configure the [Vagrantfile](https://www.vagrantup.com/docs/vagrantfile/).
        * It's a really full virtualization. We could do anything we want. It just likes a really Linux box.
            * Public IP
            * Modify `/etc/rc.local`
            * ...etc
    * cons
        * It's really slow.

I heard people would ask is Docker good to use. I think the precise question is when to use Docker.
I will list some use cases and discuss those use cases.

* Testing
    * Using Docker in testing, it's the best scenario to use Docker.
        * Due to Docker's design, immutable image provides a way to guarantee we only test the change sets we want.
    * Increase the iteration.

* Developer's Local Environment
    * We could easily replicate the whole architecture in one computer. Although, it may be not that easy. At least we could do it with Docker.

* Production
    * Without Internet Facing
        * We could use Docker safely. However I will only use it in a situation, when our environment is complex. For example, we use multiple Programming Language in production.

    * Internet Facing
        * The answer is yes and no.
            * No. Since Docker still uses Linux kernel directly. There are cases that escaping container.
            * Yes. But we have to do as much as possible to prevent breakout and monitor Docker. And running Docker on the VM not the bare machine. It could prevents the worst case scenario.
                * How to prevent breakout? There are some tips from [Using Docker](http://shop.oreilly.com/product/0636920035671.do). I will mention some of them I think those are really important.
                    * Set up User. Don't use root directly.
                    * Read-only filesystem.
                    * Be aware of some commands will rise the privileges.



