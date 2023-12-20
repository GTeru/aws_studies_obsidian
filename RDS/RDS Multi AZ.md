---
tags:
  - Disaster_recovery
---
Creation of [[RDS (Relational Database Service)]] standy instances mainly for disaster recovery, this mechanism has the following attributes:
- Synchronous data replication from master instance to standy instance.
- It also provides one unified DNS name, providing automatic app failover to standby instance
- Increases availability
- Failover in case of loss of [[AZ (Availability Zone)]], loss of network or storage failure
- No manual intervention in apps
- __Not used for scaling__
- We can also use [[RDS Read Replicas]] as multi AZ

## Single to Multi-AZ
---
- Zero downtime opeation
- Internally:
	- A snapshot is taken
	- New DB is restored from the snapshot in a new AZ
	- Synchronization is established between the two databases
