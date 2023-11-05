---
tags:
  - Database
---
AWS Managed Cache DB
- ElastiCache manages Redis or Memcached
- Caches are in-memory databases with really high performance, low latency
- Help reduce load off of DB for read intensive workloads
- Helps make your application stateless
- AWS takes care of OS maintenanace / patching, optimizations, setup, configuration, monitoring, failure recovery and backups
- __Using ElastiCache involves heavy application code changes__

## [Redis](https://redis.io) vs [Memcached](https://pt.wikipedia.org/wiki/Memcached)
---

| Redis | Memcached |
|---|---|
|Multi [[Availability Zone (AZs)]] with Auto-Failover|Multi-node for partitioning of data (sharding)|
|[[RDS Read Replicas]] to scale reads and have high availability|No high availability (replication)|
|Data durability using AOF persistence|Non persistent|
|Backup and restore features|No backup and restore|
|Supports Sets and Sorted Sets|Multi-threaded architecture|
![redis_vs_memcached.png](./Images/redis_vs_memcached.png)