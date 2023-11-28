[[AWS Lambda]] functions are launched outside your own VPC (in an AWS-owned VPC), so it cannot access your private resources (RDS, ElastiCache, internal ELB, etc...). To access the private resources in your VPC you have
1. Define VPC ID, Subnets and [[Security Groups]]
2. Lambda will create an [[Elastic Network Interfaces (ENI)]] in your subnets

## Use case: Lambda with RDS [[RDS Proxy]]
---
- If Lambda functions directly access your database, they may open too many connections under high load
- RDS Proxy
	- Improves
		- Scalability by pooling and sharing DB connections
		- Availability by reducing by 66% the failover time and preserving connections
		- Security by enforcing [[IAM]] authentication and storing credentials in Secrets Manager
- Lambda function must be deployed in your VPC, because RDS Proxy is never publicly accessible