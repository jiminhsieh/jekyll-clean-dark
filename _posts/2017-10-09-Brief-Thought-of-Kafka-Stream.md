---
layout: post
title: "Brief Thought of Kafka Stream"
date: 2017-10-09
tags: 
    - kafka
description: 
comments: true
share: true
---

After reading [Introducing Kafka Streams: Stream Processing Made Simple](https://www.confluent.io/blog/introducing-kafka-streams-stream-processing-made-simple/), I thought it is a pretty nice progress. Kafka Stream makes Kafka not only a simple high-throughput, low-latency, and fault tolerance message queue but also a **streaming processing engine**. It means it could replace some of the jobs of Spark or Flink. 

Normally, companies would use Spark or Flink to do ETL or more sophisticated and long-running analysis. But Kafka Stream seems could be used as part of real-time ETL and light-weight analysis. This point is I think a lot of company only need this capability - real time and relative light-weight processing with fault tolerance. That's Kafka Stream could step into.

As Jay Kreps mentioned, 

![img](https://cdn2.hubspot.net/hubfs/540072/A_March_10/Streams_Blog_-_1.png)

It clearly shows you the comparison of Kafka Stream with other related tech tools. 

By the way, I think Kafka's design documents is really really nice, it's a pleasure to read, after I glimpsed one of KIPs(Kafka Improvement Proposals), [Exactly Once Delivery and Transactional Messaging](https://cwiki.apache.org/confluence/display/KAFKA/KIP-98+-+Exactly+Once+Delivery+and+Transactional+Messaging).

