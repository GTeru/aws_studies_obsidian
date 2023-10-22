---
tags: []
---
- AMI are a customization of an [[EC2 (Elastic Compute Cloud)]] instance
	- You add your own software, configuration, OS, monitoring, etc...
	- Faster boot/configuration time because all packages are pre-packaged
- AMI are built for a [[AWS Region]] (but can be copied across regions)
- You can launch EC2 instances from:
	- A public AMI: AWS provided
	- Your own AMIL you make and maintain them yourself
	- An AWS Marketplace AMI: an MAI someone else made (and potentially sells)

## Creating a custom AMI
---
- Start and EC2 instance and customize it
- Stop the instance (for data integrity)
- Build and AMI - this will also create EBSs snapshots
- Launch instances from other AMIs