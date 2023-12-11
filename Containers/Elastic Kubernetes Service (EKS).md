---
tags:
  - Compute
---
Launch and manage _Kubernetes_ clusters on AWS, an alternative to [[ECS Service Auto Scaling]]
- Kubernetes is an open-source system for automatic deployment, scaling and management of containerized (usually Docker) applications
- EKS supports [[EC2 (Elastic Compute Cloud)]] if you want to deploy worker nodes or [[AWS Fargate]] to deploy serverless containers
- Use case
	- Company is already using Kubernetes on current infrastructure and wants to migrate to AWS while still using K8s
- K8s is cloud-agnostic

## EKS Node Types
---
- Managed Node Groups
	- Creates and manages Nodes (EC2 instances) for you
	- Nodes are part of an [[EC2 Auto Scaling Groups (ASG)]] managed by EKS
	- Supports On-Demand or Spot instances
- Self-managed Nodes
	- Nodes created by you and registered to the EKS cluster and managed by an ASG
	- Can leverage pre-build [[Amazon Machine Image (AMI)]] - Amazon EKS Optimized AMI
	- Supports On-Demand or Spot Instances
- [[AWS Fargate]]
	- No maintenance required; no nodes managed

## Data Volumes
---
- Need to specify __Storage Class__ manifest on your EKS cluster
- Leverages a __Container Storage Interface (CSI)__ compliant driver
- Supports for
	- [[Elastic Block Storage (EBS)]]
	- [[Elastic File System (EFS)]] (works with [[AWS Fargate]])
	- [[Amazon FSx]] for Lustre
	- Amazon FSx for NetApp ONTAP
