---
title: Real World Applications of Distributed Systems
author: Arjit Sharma
courses: ["distributed"]
categories: ["Development-Plus"]
featured: false
draft: false
---

## Messaging Systems - Kafka

Kafka is a distributed event streaming platform used for real-time data pipelines, messaging, and log aggregation.

Producers send messages to topics from where Consumers read messages at their own pace. 
This can be used in Event-driven microservices or real-time analytics.

## Coordination Service -  Apache Zookeeper

Apache Zookeeper is a **distributed coordination service** used for managing configurations, leader election, and synchronization in distributed systems.
It maintains a heirarchial key-value store, where clients connect to its nodes for leader election, locking or configuration management. It uses leader-follower model.

## Distributed Databases - Apache Cassandra

Apache Cassandra is a **highly available, distributed NoSQL database** designed for handling massive amounts of data across multiple nodes.
It uses peer-to-peer architecture, stores data in columnar format and uses partition and replication as well.