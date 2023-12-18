---
tags:
  - Network
  - Security
---
- Virtual Private Network (VPN) that connects your [[VPC (Virtual Private Cloud)]] to a private corporate network
- To setup a connection you need two components:
	1. [[VPG (Virtual Private Gateway)]]
	2. Customer Gateway (CGW)
		- Software application or physical device on customer side of the VPN connection
		- [Devices tested](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html)

## Connection setup
---
- Customer gateway device (On-premises)
	- What IP address to use?
		- Public Internet-routable IP address for your Customer Gateway device
		- If it's behind a NAT device that's enabled for NAT traversal (NAT-T), use the public IP address of the NAT device
- Important step: enable __Route propagation__ for Virtual Private Gateway in the [[Route Table]] that is associated with your [[Subnet]]s
- If you need to ping your [[EC2 (Elastic Compute Cloud)]] instances from on-premises, make sure you add the ICMP protocol on the inbound of your [[Security Group]]

## VPN CloudHub
---
- Provide secure communication between multiple sites, if you have multiple VPN connection
- Low-cost hub-and-spoke model for primary or secondary network connectivity between different locations (VPN only)
- It's a VPN connection so it goes over the public internet
- To set it up, connect multiple VPN connections on the same VGW, setup dynamic routing route tables
