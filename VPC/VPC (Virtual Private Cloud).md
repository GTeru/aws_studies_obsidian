---
tags:
  - Network
---
- You can have a multiple VPCs in an [[AWS Region]] (max. 5 per region - soft limit)
- Max [[CIDR]] per VPC is 5, for each CIDR
	- Min. size is /28 (16 IP addresses)
	- Max. size is /16 (65.536 addresses)
- Because VPC is private, only the Private IPv4 ranges are allowed
	- 10.0.0.0 - 10.255.255.255 (10.0.0.0/8)
	- 172.16.0.0 - 172.31.255.255 (172.16.0.0/12)
	- 192.168.0.0 - 192.168.255.255 (192.168.0.0/16)
__Your VPC CIDR should NOT overlap with your other networkds (e.g.: corporate)__