---
tags:
  - Network
---
- Allow resources (e.g.: [[EC2 (Elastic Compute Cloud)]] instances ) in a [[VPC (Virtual Private Cloud)]] connect to the internet
- It scales horizontally and is highly available and redundant
- Must be created separately from a VPC
	- One VCP can only be attached to one IGW and vice versa
- Internet Gateways on their own do not allow Internet access, you must also configure [[Route Table]]
