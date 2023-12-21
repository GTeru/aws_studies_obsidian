---
tags:
  - Disaster_recovery
---
- Quickly and securely migrate databases to AWS, resiliently and self healing
- The source database remains available during the migration
- Supports
	- Homogeneous migrations. Ex Oracle to [[RDS (Relational Database Service)]] Oracle
	- Heterogeneous migrations. Ex. Microsoft SQL Server to [[Amazon Aurora]]
- Continuous Data Replication using CDC
- Must create an [[EC2 (Elastic Compute Cloud)]] instance to perform the replication tasks

## Sources and Targets
---
- Source
	- On-premises and EC2 instances databases
	- Azure: Azure SQL Database
	- Amazon RDS: all including Aurora
	- [[S3 (Simple Storage Service)]]
	- [[Amazon DocumentDB]]
- Target
	-  On-premises and EC2 instances databases
	- RDS
	- [[RedShift]], [[DynamoDB]], S3
	- [[OpenSearch]] Service
	- [[Kinesis Data Streams]]
	- Apache Kafka
	- DocumentDB & [[Amazon Neptune]]
	- Redis & Babelfish

## AWS Schema Conversion Tool (SCT)
---
- Convert Database's Schema from one engine to another (e.g.: Postgre to MySQL)
- Works for OLTP and OLAP

## DMS - Multi-AZ Deployment
---
- When multi-[[AZ (Availability Zone)]] is enabled, DMS provisions and maintains a synchronously stand replica in a different AZ
- Advantages
	- Provides data redundancy
	- Eliminates I/O freezes
	- Minimizes latency spikes
