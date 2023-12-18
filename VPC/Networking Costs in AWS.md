---
tags:
  - Network
---
## Data transit cost per GB
---
Traffic inbound/between [[EC2 (Elastic Compute Cloud)]] instances are charged over GB:
- Use private IP instead of public IP for good savings and better network performance
	- Free between EC2 instances in the same [[AZ (Availability Zone)]]
	- $0.01/Gb using private IP
	- $0.02/Gb using public IP
- Use the same AZ for maximum savings (at the cost of high availability)
	- $0.02/Gb inter-region

## Minimizing egress traffic network cost
---
- Egress traffic: outbound traffic (from AWS to outside)
- Ingress traffic: inbound traffic - from outside to AWS (typically free)
- Try to keep as much internet traffic within AWS to minimize costs
- [[DX (Direct Connect)]] location that are co-located in the same [[AWS Region]] results in lower cost for egress network

## S3 Data Transfer Pricing
---
- [[S3]] ingress is free
- S3 to internet -> $0.09 per GB
- S3 transfer acceleration
	- Faster transfer time (50 to 500% better)
	- Additional cost on top of data transfer pricing: +$0.04 to $0.08 per Gb
- S3 to [[CloudFront]] is free
- Cloudfront to Internet: $0.085 per Gb (slightly cheaper than S3)
	- Caching capability (lower latency)
	- Reduce costs associated with S3 Requests Pricing (7x cheaper with CloudFront)
- [[S3 Replication]] (Cross-region): $0.02 per GB

## NAT Gateway vs Gateway VPC Endpoint
---
- Use VPC Endpoint when you need to transfer data into S3 bucket, which saves you in
	- $0.045 [[NAT Gateway]]/hour
	- $0.045 NAT Gateway/data processed \* GB
	- Data transfer out to S3
		- $0.9 cross-region
		- $0.00 same-region