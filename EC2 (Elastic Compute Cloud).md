Service that lets you rent virtual machines.
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
m5.2xlarge

m : instance class
5 : generation
2xlarge : size of the class (how much RAM, CPU it has)
### Example table
| Instance | vCPU | Mem(GiB) | Storage | Network Performance | EBS Bandwidth|
|---       |---   |---       |---      |---                  |---           |
|t2.micro  | 1|1|EBS-Only|Low to Moderate||
|c5d.4xlarge|16|32|1 x 400 NVMe SSD|Up to 10 Gbps||
|r5.16xlarge|64|512|EBS Only|20Gbps|13.600|
|m5.8xlarge|32|128|EBS Only|10Gbps|6.800|
## Security Groups
---
Fundamental network security object in AWS
Control how traffic is allowed into or out of the EC2 instances, they act as a firewall to the instances, allowing certain **IP ranges** to communicate to the instances via certain **ports** with certain **protocols**

- Security groups can be attached to multiple EC2 instances and they're also locked out by region/VPC componation
- **Timeout error** probably means that a security groups has blocked the access to the instance.
- **Connection refused** probably means that there was an application error or it's not lanched.
- All inbount traffic is **blocked** by default
- All outbound traffic is **authorised** by default
- It's also possible to allow access to a security group from inside another security group. So if instance A allows security group X and Y to access the instance, all instances that have either X or Y attached to them, can also communicate with A. That's a super neat feature we can use to simplify communication inside the same VPC.

## Importante Ports
---
- 22 (SSH - Secure Shell): log into a Linux instance
- 21 (FTP - File Transfer Protocol): upload files into a file share
- 22 (SFTP - Simple File Transfer Protocol): upload files using SSH
- 80 (HTTP - Hypertext Transfer Protocol): access unsecured websites
- 443 (HTTPS - ): access secured websites
- 3389 (RDP - Remote Desktop Protocol): log into a Windows instance

## Purchasing Options
---
- On-Demand: You need, we give
- Spot instances: You bid a max price you're willing to pay for the instance and it provides it, but the instance can be taken out of you if the market price gets higher than what you're willing to pay for.
- Reserved Instance: Reserve some instances
- EC2 Savings Plan: Long term plan specifying the instance family & AWS region for a minimum amount
- Reserved Converible Instance: Same as reserved, but with OS and class flexibility
- Dedicated Host: Book an entire physical server, which is good for more complex hardware or business needs
- Capacity Reservation: reserve specific capacity on an AZ for any amount of time, charged the same as the On-Demand option.