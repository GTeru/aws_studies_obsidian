- [[EC2 (Elastic Compute Cloud)]] can use the VPC Endpoints to connect with services that are inside AWS network, but out of your [[VPC (Virtual Private Cloud)]].

## AWS PrivateLink
---
- Every AWS service is public exposed (public URL)
- VPC Endpoints (powered by AWS PrivateLink) allows to connect to AWS services using a __private network__ instead of using the public Internet
- They're redundant and scale horizontally
- They remove the need of [[IGW (Internet Gateway)]], [[NAT Gateway]], etc... to access AWS services
	- Reduced cost
	- Less overhead because there's less hops
- In case of issues
	- Check DNS Settings Resolution in your VPC
	- Check [[Route Table]]

## Type of Endpoints
---
- Interface Endpoints (powered by PrivateLink)
	- Provisions an [[ENI (Elastic Network Interfaces)]] (private IP address) as an entry point (must attach a [[Security Group]])
	- Supports most AWS services
	- $ per hour + $ per GB of data processed
- Gateway Endpoints
	- Provisions a gateway and must be used _as a target in a route table (does not use security groups)_
	- Supports only [[S3 (Simple Storage Service)]] and [[DynamoDB]]
	- Free

### Gateway or Interface Endpoint for S3?
- Gateway is mostly preferred
	- Free cost
- Interface is preffered when
	- Access is required from on-premises ([[Site-to-Site VPN]] or [[DX (Direct Connect)]])
	- Different VPC
	- Different [[AWS Region]]