---
tags:
  - Network
---
Logical component in a [[VPC]] that represents a virtual network card
The ENI can be attached to an [[EC2 (Elastic Compute Cloud)]] instances but they're treated as it's own object that can be attached, moved from EC2 instances or other components of a VPC, for example in the case of a failure of one of the EC2 instance.
## Attributes
---
- Primary private IPv4, one or more secondary IPv4
- One Elastic IP (IPv4) per private IPv4
- One Public IPv4
- One or more security groups
- A MAC Address
- They're bound to a specific [[Availability Zone (AZs)]]