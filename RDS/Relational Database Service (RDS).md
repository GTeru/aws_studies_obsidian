---
tags:
  - Database
---
Service that allows creation of databases that are managed by AWS.
- Postgres
- MySQL
- MariaDB
- Oracle
- Microsoft SQL Server
- Aurora (AWS Proprietary database) 

RDS is a managed service
- Automated provisioning, OS patching
- Continuous backups and restoration to specific timestamp
- Monitoring dashboards
- Read replicas for improved read permformance
- Multi AZ setup for DR (Disaster Recovery)
- Maintenance windows for upgrades
- Scaling capability (vertical and horizontal)
- Storage backend by [[Elastic Block Storage (EBS)]] (gp2 or io1)
- __CAN'T__ SSH into instances (except Oracle and Microsoft SQL Server with [[RDS Custom]])

## Storage Auto Scaling
---
- Helps increase storage RDS DB instances dynamically
- When EDS detects yo are running out of free database storage, it scales automatically
- Avoid manually scaling your database storage
- Manually set __Maximum Storage Threshold__ (maximum limit for DB storage)
- Automatically modify storage if:
	- Free storage is less than 10% of allocated storage
	- Low-storage lasts at least 5 minutes
	- 6 hours have passed since last modification
- Suports all RDS database engines
