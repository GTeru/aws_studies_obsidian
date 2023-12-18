---
tags:
  - Disaster_recovery
---
- Any event that has a negative impact on a company's business continuity or finances is a disaster
- Disaster recovery (DR) is about preparing for and recovering from a disaster
- Types of disaster recovery
	- On-premise -> on-poremise: traditional DR and very expensive
	- On-premise -> AWS Cloud: hybrid recovery
	- [[AWS Region]] A -> AWS Region B

# RPO (Recovery Point Objective)
---
- Point in time a "backup" is created and that we can go back to in case of a disaster
- Delta between this RPO and the disaster is the timeframe we have __data loss__

## RTO (Recovery Time Objective)
---
- Point in time the application starts/works normally again.
- Delta between RTO and disaster is the timeframe we have __downtime__


## DR Strategies
---
From faster to slower RTO, we have the following DR Strategies for hybrid On-premises and Cloud:
1. Backup and Restore (High RPO)
	- Scheduled backups allow restoration of systems
	- Cheaper and easier to setup/manage
	- Example
		- [[S3]] objects transfer to Glacier class
		- [[EBS (Elastic Block Storage)]], [[RDS (Relational Database Service)]], [[RedShift]] volumes snapshots
2. Pilot Light
	- A small version of the app is always running in the cloud
	- Useful for critical core app (pilot light)
	- Very similar to Backup and Restore
	- Faster than backup and restore as critical systems are already up
		- Example
			- Continuous data replication in RDS core application, if disaster happens [[Route53]] can redirect the traffic from the failing app to a new [[EC2 (Elastic Compute Cloud)]] that will start the application
3. Warm Standby
	- Full system is up and running, but at minimum size
	- Upon disaster, we can scale to production load
	- Example
		- Same example as Pilot Light, but we have an [[EC2 Auto Scaling Groups (ASG)]] set to a minimum and when disaster happens, it automatically scales the application up as needed.
4. Hot Site / Multi Site Approach
	- Very low RTO (minutes or seconds) - very expensive
	- Full production scale is running in AWS and On-premise
	- Example
		- Same example as Warm Standby, but ASG is set as production always
