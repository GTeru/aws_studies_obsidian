---
tags:
  - Network
---
- Internet Assigned Numbers Authority (IANA) established certain blocks of IPv4 addresses for the use of private (LAN) and public (Internet) addresses
- __Private IP__ can only allow certain values (IP range and [[CIDR]])
	- 10.0.0.0 - 10.255.255.255 (10.0.0.0/8) - in big networks
	- 172.16.0.0 - 172.31.255.255 (192.168.0.0/16) - AWS default VPC in that range
	- 192.168.0.0 - 192.168.255.255 (192.168.0.0/16) - small networks e.g. home networks
- All the rest of the IP addresses on the internet are public