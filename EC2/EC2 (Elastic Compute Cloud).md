---
tags:
  - Compute
---
Service that lets you rent virtual machines.
If you w[[IAM]]ant to have AWS capabilities within your instances, you need to attach a **[[IAM]] role** with the desired capabilities to them!

## Services
---
- Elastic Compute Cloud EC2 (EC2) - renting virtual machines
- Elastic Block Storage (EBS) - Storing data on virtual drives
- Elastic Load Balancer (ELB) - Distributing load across machines 
- Auto Scaling Group (AGS) - Scaling services using and auto-scaling group

## Types of machines
---
- General Purpose: Has a good balance between compute, memory, networking (e.g. t2.micro)
- Compute optimized (c5.micro)
- Memory optimized (r5.small)
- Storage optimized (h5.small)
For a complete list of available ec2 instance types, [click here](https://aws.amazon.com/ec2/instance-types/)
### General rule 
|Type|Class|Hardware generation|Size (CPU, RAM)|
|---|---|---|---|
|m5.2xlarge|m|5|2xlarge|
### Example table
| Instance | vCPU | Mem(GiB) | Storage | Network Performance | EBS Bandwidth|
|---       |---   |---       |---      |---                  |---           |
|t2.micro  | 1|1|EBS-Only|Low to Moderate||
|c5d.4xlarge|16|32|1 x 400 NVMe SSD|Up to 10 Gbps||
|r5.16xlarge|64|512|EBS Only|20Gbps|13.600|
|m5.8xlarge|32|128|EBS Only|10Gbps|6.800|

## Purchasing Options
---
- On-Demand: You need, we give
- Spot instances: You bid a max price you're willing to pay for the instance and it provides it, but the instance can be taken out of you if the market price gets higher than what you're willing to pay for.
- Reserved Instance: Reserve some instances
- EC2 Savings Plan: Long term plan specifying the instance family & [[AZ (Availability Zone)]] for a minimum amount
- Reserved Converible Instance: Same as reserved, but with OS and class flexibility
- Dedicated Host: Book an entire physical server, which is good for more complex hardware or business needs
- Capacity Reservation: reserve specific capacity on an AZ for any amount of time, charged the same as the On-Demand option.