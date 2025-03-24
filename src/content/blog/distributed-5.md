---
title: Distributed System Trade-offs (CAP & Beyond)
author: Arjit Sharma
courses: ["distributed"]
categories: ["Development-Plus"]
featured: false
draft: false
---

## CAP Theorem

![image.png](https://res.cloudinary.com/dwa6rcttw/image/upload/v1742841485/image_iveq67.png)

It is impossible for a distributed data store to guarantee all three of the following properties - 

- Consisteny (C) - Every read gets latest write.
- Availability (A) - Every request gets a response.
- Partial Tolerance (P) - System continues working despite network failures.

Or more correctly -

“ A distributed system can be either *consistent* or *available* in the presence of a network partition. “

We prioritize Consistency in Banking transactions, Stock trading systems, while for Social media feeds and E-commerce carts, Availability is prioritized.

*Note - ACID focusses on ensuring integrity and reliability of individual transaction in system while CAP deals with broader trade-offs across distributed system*

## PACELC theorem

The **PACELC theorem** extends CAP by addressing what happens when there is **no partition**:

- If a partition occurs (P), the system must choose between Availability (A) and Consistency (C).
- Else (E), when there is no partition, the system must choose between Latency (L) and Consistency (C).

Example - Amazon DynamoDB is PA/EL (chooses availability during partitions but optimizes for low latency when there are no partitions. Google Spanner is PC/EC (chooses Consistency in all cases)