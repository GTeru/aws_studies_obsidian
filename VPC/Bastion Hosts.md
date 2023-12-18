---
tags:
  - Network
  - Security
---
- It's a special [[EC2 (Elastic Compute Cloud)]] instance that is on a Public [[Subnet]] from the [[VPC (Virtual Private Cloud)]] but it has access to the EC2 instances from the Private Subnet
	- We can use a Bastion Host to SSH into our private EC2 instances
- Bastion Host [[Security Group]] must allow inbound from the internet on port 22 from restricted [[CIDR]], for example the __public CIDR__ or your corporation
- Security group of the private EC2 instances must allow the security group of the Bastion Host, or the __private IP__ of the bastion host