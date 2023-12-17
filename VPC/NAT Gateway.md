---
tags:
  - Network
---
- AWS-managed NAT, higher bandwidth, high availability and no administration
	- A better solution to grant internet access capabilities to [[EC2 (Elastic Compute Cloud)]] instances that are in a private [[Subnet]]
	- 5 Gbps of bandwidth with automatic scaling up to 100Gbps
- Pay per hour for usage and bandwidth
- NAT Gateway is created in a specific [[AZ (Availability Zone)]], uses an Elastic IP
- Can't be used by EC2 instance in the same subnet (only from other subnets)
- Requires an [[IGW (Internet Gateway)]] (Private Subnet -> NAT Gateway -> IGW)
- No [[Security Groups]] are required

## High Availability
---
- NAT Gateway is resilient within a single AZ
- Must create multiple NAT Gateways in multiple AZs for fault-tolerance
- There is no cross-AZ failover needed because if an AZ goes down it doesn't need NAT