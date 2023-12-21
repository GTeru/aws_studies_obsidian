---
tags:
  - Compute
---
## EC2 Launch Type
---
- Launch Docker container on AWS = Launch __ECS Tasks__ on ECS Clusters
- [[EC2 (Elastic Compute Cloud)]] Launch Type - you must provision & maintain the infrastructure (EC2 instances)
- Each EC2 instance must run the ECS Agent to register in the ECS Cluster
- AWS takes care of starting / stopping containers

## Fargate Launch Type
---
- Launch Docker containers on AWS
- Don't need to provision the infrastructure
- It's _serverless_
- You need to create task definitions
- AWS just runs ECS Tasks for you based on the CPU/RAM you need
- To scale, just increase the number of tasks - no more EC2 instances

## Permissioning & Security
---
Leverages [[IAM]] roles for permissioning
- EC2 instance Profile (EC2 Launch Type Only)
	- Used by the ECS Agent
	- Makes API calls to ECS service
	- Send container logs to [[CloudWatch]] Logs
	- Pull Docker image form [[ECR (Elastic Container Registry)]]
	- Reference sensitive data in Secrets Manager or SSM Parameter Store
- ECS Task Role
	- Allows each task to have a specific role
	- Use different roles for the different ECS services you run
	- Task role is definied in the __task definition__

## Load Balancer Integrations
---
- [[ALB (Application Load Balancer)]] supported and works for most use cases
- [[NLB (Network Load Balancer)]] recommended only for high throughput/high performance use cases, or to pair it with AWS Private Link
- Classic Load Balancer supported but not recommended (no advance features, e.g.: no [[AWS Fargate]])

## Data Volumes
---
- Mount [[EFS (Elastic File System)]] file system onto ECS tasks
- Works for both EC2 and [[AWS Fargate]] launch types
- Tasks running in any [[AZ (Availability Zone)]] will share the same data in the EFS file system
- [[AWS Fargate]] + EFS = Serverless
- Use cases
	- Persist multi-AZ shared storage for your containers
- Not 
	- Amazon [[S3 (Simple Storage Service)]] cannot be mounted as a file system