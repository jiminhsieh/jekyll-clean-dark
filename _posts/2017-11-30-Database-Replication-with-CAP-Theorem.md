---
layout: post
title: "Database Replication with CAP Theorem"
date: 2017-11-27
tags: 
    - database
    - postgresql
    - cap
description:
comments: true
share: true
---

Precisely speaking, this post is about [Postgres-BDR](https://www.2ndquadrant.com/en/resources/bdr/) and CAP theorem. However, what I am talking about is not only could be applied to Postgres-BDR.  

# Intro
I had needed to evaluate replication of PostgreSQL recently. One of the tools I had to evaluate is Postgres-BDR. Basically, Postgres-BDR is a Master-Master tool to replicate data cross different PostgreSQLs.

What's the relationship of database replication and CAP theorem? 
* After I read through [documents](http://bdr-project.org/docs/stable/bdr-concepts.html) of Postgres-BDR. I found this phrase: *asynchronous replication is often called an "eventually consistent"*. That's one of properties of CAP theorem - consistency. 
* CAP theorem is used to discuss any **networked shared-data systems**. Multi-node of RDBMS is just subset of that kind of system.

After I found this relationship between Postgres-BDR and CAP theorem. I experimented with Postgres-BDR in a very limited resource to form my hypothesis.


# Ｗhat did I learn from Postgres-BDR and CAP theorem?

* CAP theorem is still a theorem could help you to deal with the problems related to distributed storage system . Although there were some debates in the early year. The points are:
    * Consistency (C) and high availability (A). You don't have to pick one of them.  
    * Consistency and high availability are more like percentile in the abstract. You could pick 70 % of C and 30 % A.
    
* Performance
    * When you decide toward to more availability, you could gain more throughput. The reason for it is you have to do replication in the manner of synchronousness. You simply don't need to wait for replication finish.
        * That's one of the reasons why Postgres-BDR is really fast. (Another reason is Postgres-BDR replicates from WAL (Write-Ahead Logging).) 
    * In contrast, more consistency means more latency because of you have to replicate synchronously.
        * In DynamoDB, it supports *Eventually Consistent Reads* and *Strongly Consistent Reads*. AWS also mentions:
        > [a strongly consistent read might **take more time** than an eventually consistent read, it always returns the last updated value](http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_GetItem.html)

* How could CAP exist at the same time?
    * How you limit the behavior of accessing distributed storage system?
    * How you resolve the conflict? 


References: 

1. [BDR overview](http://bdr-project.org/docs/stable/overview.html)
    * The documentation of Postgres-BDR is really great and well written. I encourage anyone who is interested in database, replication, or NoSQL could read the link. 
2. [CAP Twelve years later: How the "Rules" have Changed](https://www.researchgate.net/profile/Eric_Brewer3/publication/220476881_CAP_Twelve_years_later_How_the_Rules_have_Changed/links/56a644b108ae2c689d39e3ba/CAP-Twelve-years-later-How-the-Rules-have-Changed.pdf?origin=publication_detail) by Eric Brewer at ResearchGate
3. [CAP and Architectual Consequences](https://www.youtube.com/watch?v=LW8MBYU_pzQ) by Martin Schoenert
