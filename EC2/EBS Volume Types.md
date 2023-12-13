---
tags: []
---
Information about [[EBS (Elastic Block Storage)]] volume types:
	- __gp2 / gp3__ (SSD): General purpose SSD volume that balances price and performance for a wide variety of workloads
	- __io1 / io2__ (SSD): Highest-performance SSD volume for mission-critical low lattency or high-throughput workloads
	- __st1__ (HDD): Low cost HDD volume designed for frequently accesssedm throughput-intensive workloads
	- __sc1__ (HDD): Lowest cost HDD volume designed for less frequently accessed workloads
EBS volumes are characterized in Size, Throughput, IOPS (I/O operations per second)
More about volume types in this [link](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html)

## General Purpose SSD (gp2, gp3)
---
- Cost effective storage, low-latency
- System boot volumes, Virtual desktops, Development and test environments
- 1 GiB - 16TiB
### gp2
- Small gp2 volume burst IOPS to 3.000
- Size of the volume and IOPS are linked, max IOPS is 16.000
- 3 IOPS per GB, means at 5.334 GB we are at the max IOPS
### gp3
- Baseline of 3.000 IOPS and throughput of 125 MiB/s
- Can increase IOPS up to 16.000 and throughput up to 1.000MiB/s independently

## Provisioned IOPS (PIOPS) SSD
---
- Critical business applications with sustained IOPS performance
- Applications that need more than 16.000 IOPS
- Great for DB workloads (sensitive to storage perf and consistency)
- io1 / io2 (4GiB - 16GiB)
	- Max PIOPS: 64.000 for Nitro EC2 instances and 32.000 for other
	- Can increase PIOPS independently from storage size
	- io2 have more durability and more IOPS per GiB (at the same price as io1)
- io2 Block Express (4GiB - 64 GiB):
	- Sub-milisecond latency
	- Max PIOPS: 256.000 with an IOPS: GiB increase ratio of 1.000:1
	- Supports EBS Multi-attach

### Hard Disk Drives (HDD)
- Cannot be a boot volume in EC2 instances
- 125 GiB to 16TiB
- Throughput optimized HDD (st1)
	- Big Data, Data Warehouses, Log Processing
	- Max throughput 500 MiB/s - max IOPS 500
- Cold HDD (sc1):
	- For data that is infrequently accessed
	- Scenarios where lowest cost is important
	- __Max throughput__ 250MiB/s - max IOPS 250 