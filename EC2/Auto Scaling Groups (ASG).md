Mechanism to scale [[EC2 (Elastic Compute Cloud)]] instances depeding on the load of the application
- Scale-out to increase instances
- Scale-in to decrease instances

## Use cases
---
- Ensure a minumum and maximum number of EC2 instances running
- Automatically register new instances to a [[ELB (Elastic Load Balancer)]]
- Re-create an EC2 instance in case a previous one is terminated (e.g.: it becomes unhealthy)

__ASGs are free, you only use the underlying resources created__

To create an autoscaling group you'll need to create a __Launch Template__, which are instructions of how to start an EC2 instance, these configurations include:
- [[AMI (Amazon Machine Image)]] + Instance Type
- EC2 User Data
- EBS Volumes
- [[Security Groups]]
- SSH Key Pair
- [[IAM]] Roles
- Network + Subnets information
- [[ELB (Elastic Load Balancer)]] information

Other configurations:
- Min size
- Max size
- Initial Capacity


It's also possible to integrate ASG with [[CloudWatch]] alarms and triggers.