- Automated backups of [[Relational Database Service (RDS)]]
	- Daily full backup of the DB (during backup window)
	- Transaction logs are backup by RDS every 5 minutes
	- Restore at any point in time
	- 1 to 35 days of retention, set 0 to disable automated backups
- Manual DB Snapshots
	- Triggered by the user
	- Retentionof backup for as long as you want
- Trick: if a stopped RDS DB has intermittent use, you can snapshot the database and restore when you need to use it again. This is cheaper because snapshot storage is cheaper than the database storage.

## [[Amazon Aurora]] Backups
---
- Automated backups
	- 1 to 35 days (cannot be disabled)
	- point in time recovery in that timeframe
- Manual DB Snapshots
	- Triggered by the user
	- Retention of backup for as long as you want

## RDS & Aurora Restore options
---
- Restoring a RDS / Aurora backup or a snapshot creates a new database
- Restoring MySQL RDS database from [[S3]]
	- Create a backup of your on-premises database
	- Store it on S3 (object storage)
	- Restore backup file onto a new RDS instance running MySQL
- Restoring MySQL Aurora cluster from S3
	- Create a backup of your on-premises database using Percona XtraBackup
	- Store backup file on S3
	- Restore the backup file onto a new Aurora file using MySQL

## Aurora Database Cloning
---
- Create a new Aurora DB Cluster from an existing one
- Faster than snapshot & restore
- Uses __copy-on-write__ protocol
	- Initially tha new DB cluster uses the same data volume as the original DB cluster (fast and efficient - no copying is needed)
	- When updates are made to the new DB cluster data, then additional storage is allocated and data is copied to be separated
- Very fast & cost-effective
- Useful to create a "staging" DB from a "production" DB without impacting the production DB