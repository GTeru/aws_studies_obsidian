---
tags: []
---
- Sometimes you want to control over the [[EC2 (Elastic Compute Cloud)]] isnstance placemente strategy, for example if you have many services in different instances and you want to reduce latency.
- There's 3 types of strategies:
	1. Cluster - cluster instances into low-latency group in a single AZ
	2. Spread - spreads instances across underlying hardware (max 7 instances per group per [[Availability Zone (AZs)]]) - critial applications
	3. Partition - spreads instances across many different partitions (which rely on different sets of racks or hardware) within an AZ. Scales to 100s of instances per group - Hadoop, Cassandra, Kafka
## Cluster
---
All the instances stay on the same hardware and AZ
- __Pros__ 
	- Great network (10 Gbps bandwidth betweem instances)
- __Cons__
	- If hardware fails, all instances fails at the same time
- __Use cases__
	- Big Data job that needs to complete fast
	- Application that needs extremely low latency and high network throughput
## Spread
---
All instances are on different hardware and AZ
- Pros
	- Can span across AZs
	- Reduced risk of simultaneous failure
	- Instances are on different physical hardware
- Cons
	- Limited to 7 instances per AZ per placement group
- Use Cases
	- Applications that needs to maximize availability
	- Critical Applications where each instance must be isolated from failure from each other
## Partition
---
Instances are partitioned between physical hardware
- Up to 7 partitions per AZ
- Can span across multiple AZs in the same region
- Up to 100s of instances
- Instances in a partition do not share hardware with instances in other partitions
- A partition failure can affect many EC2 instances but won't affect other partitions
- EC2 instances get access to the partition information as metadata
- Use cases: HDFS, HBase, Cassandra, Kafka