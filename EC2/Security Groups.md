---
tags:
  - Security
  - Network
---
Fundamental network security object in AWS
Control how traffic is allowed into or out of the [[EC2 (Elastic Compute Cloud)]] instances, they act as a firewall to the instances, allowing certain **IP ranges** to communicate to the instances via certain **ports** with certain **protocols**

- Security groups can be attached to multiple EC2 instances and they're also locked out by region/[[VPC]] componation
- **Timeout error** probably means that a security groups has blocked the access to the instance.
- **Connection refused** probably means that there was an application error or it's not lanched.
- All inbount traffic is **blocked** by default
- All outbound traffic is **authorised** by default
- It's also possible to allow access to a security group from inside another security group. So if instance A allows security group X and Y to access the instance, all instances that have either X or Y attached to them, can also communicate with A. That's a super neat feature we can use to simplify communication inside the same VPC.