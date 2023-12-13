Automatically increase/decrease the desired number of __ECS tasks__ based on different kind of metrics
- Amazon [[ECS (Elastic Container Service)]] Auto Scaling uses __AWS Application Auto Scaling__
	- ECS Service Average CPU Utilization
	- ECS Service Average Memory Utilization - Scale on RAM
	- ALB request count per target - metric coming from the [[ALB (Application Load Balancer)]]
- Target tracking - scale based on target value for a specific [[CloudWatch]] metric
- Step scaling - scale based on specific CloudWatch alarm
- Scheduled scaling - scale based on specific date/time (predictable changes)
- ECS Service Auto Scaling (task level) is different of EC2 [[EC2 Auto Scaling Groups (ASG)]] ([[EC2 (Elastic Compute Cloud)]] instance level)
- [[AWS Fargate]] Auto Scaling is much easier to setup (because it's _Serverless_)

## Auto Scaling EC2 Instances
---
- Accomodates ECS Service Scaling by adding underlying EC2 instances
- ASG scaling
	- Scale based on CPU Utilization
	- Add EC2 instances over time
- ECS Cluster Capacity Provider (recommended)
	- Used to automatically provision and scale the infrastructure for your ECS Tasks
	- Capacity provider paired with an ASG
	- Add EC2 instance when missing capacity (CPU, RAM, etc...)