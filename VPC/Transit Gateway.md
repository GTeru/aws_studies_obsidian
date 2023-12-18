---
tags:
  - Network
---
- For having transitive peering between thousands of [[VPC (Virtual Private Cloud)]] and on-premises, hub-and-spoke connections
- Regional resource, can work cross-[[AWS Region]]
- Share cross-account using Resource Access Manager (RAM)
- You can peer Transit Gateways across regions
- [[Route Table]]: limit which VPC can talk with other VPC
- Works with Direct Connect Gateway, VPN connections
- Supports __IP Multicast__ (not supported by any other AWS service)

## [[Site-to-Site VPN]] ECMP
---
- ECMP - Equal-Cost Multi-Path routing
- VPN connection uses 2 tunnels
- Routing strategy to allow to forward packet over multiple best path
- Use case
	- Create multiple Site-to-Site VPN connections to __increase the bandwidth of your connection to AWS__

## Share [[DX (Direct Connect)]] between multiple accounts
---
- Connect two or more DX connections to a unique Transit Gateway