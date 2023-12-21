---
tags:
  - Network
---
- Provides a dedicated __private__ connection from a remote network to your [[VPC (Virtual Private Cloud)]] from a physical location
	- Check private locations [here](https://aws.amazon.com/directconnect/locations/)
- Dedicated connection must be setup between your DC and AWS Direct Connect locations
	- You can setup multiple DC connections within your coporate network and DC connection locations to achieve higher resiliency
	- There's also the possibility of using a backup DX connection or [[Site-to-Site VPN]] for higher availability
- You need to setup a [[VPG (Virtual Private Gateway)]] on your VPC
- Access public resources ([[S3 (Simple Storage Service)]]) and private ([[EC2 (Elastic Compute Cloud)]]) on the same connection
- Use cases
	- Increase bandwidth throughput - working with large data sets - lower cost
	- More consistent network experience - applications using real-time data feeds
	- Hybrid environments (on-premises + cloud)

## Direct Connect Gateway
---
- If you want to setup a Direct Connect to one or more VPC in many different [[AWS Region]] (same account), you must use a Direct Connect Gateway
![dx_gateway.png](dx_gateway.png)

## Connection Types
---
- Dedicated Connections: 1Gbps, 10Gbps and 100Gbps capacity
	- Physical ethernet port dedicated to a customer
	- Request made to AWS first, then completed by AWS Direct Connect Partners
- Hosted Connections: 50Mbps, 500Mbps to 10Gbps
	- Connection request are made via AWS Direct Connect Partners
	- Capacity can be added or removed on demand
	- 1, 2, 5, 10 Gbps available at selected AWS Direct Connect Partners
- Lead times are often longer than 1 month to establish a new connection

## Encryption
---
- Data in transit is __not encrypted__ but is private
- AWS Direct Connection + VPN provides IPsec-encrypted private connection
- Good for an extra level of security, but slightly more complex to put in place
