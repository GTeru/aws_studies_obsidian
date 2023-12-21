## DynamoDB Accelerator (DAX)
---
- In-memory cache for DynamoDB
- Help solve read congestion by caching
- Microseconds latency for cached data
- Doesn't require application logic modification (compatible with existing DynamoDB APIs)
- Default 5 minutes TTL for cache

### DAX vs. [[Amazon ElastiCache]]
|Dax|ElastiCache|
|---|---|
|Store Aggregation Result|Individual objects cache / Query & Scan cache|

## Stream Processing
---
- Ordered stream of item-level modifications (create/update/delete) in table
- Use cases
	- React to changes in real-time
	- Real-time usage analytics
	- Insert into derivative tables
	- Insert cross-region replication
	- Invoke [[AWS Lambda]] on changes to DynamoDB tables

Stream processing types
1. DynamoDB Streams
	- 24 hours retention
	- Limited number of consumers
	- Process using Lambda triggers or DynamoDB Kinesis adapter
2. [[Kinesis Data Streams]] (newer)
	- 1 year retention
	- High number of consumers
	- Process using Lambda, [[Kinesis Data Analytics]], [[Kinesis Data Firehose]], [[AWS Glue]] Streaming ETL, etc...


## Global Tables
---
- Tables that are not limited to a [[AWS Region]]
- Make DynamoDB table accessible with low latency in multiple regions
- Active-active replication
- Applications can read and write to tables in any region
- Must enable DynamoDB Streams as a pre-requisite

## TTL
---
- Automatically delete items after an expiry timestamp
- Use cases
	- Reduce stored data by keeping only current items
	- Web session handling
	- Adhere to regulatory obligations

## Backups for Disaster recovery
---
- Continuous backups using point-in-time recovery (PITR)
	- Optionally enabled for the last 35 days
	- Point-in-time recovery to any time withing the backup window
	- Recovery process creates a new table
- On-Demand backups
	- Full backups for long-term retention, until explicitely deleted
	- Doesn't affect performance or latency
	- Can be configured and managed in AWS Backup (enables cross-region copy)
	- Recovery process creates a new table

## Integrations with [[S3 (Simple Storage Service)]]
---
- Export to S3 (must enable PITR)
	- Works for any point in time in the last 35 days
	- Doesn't affect read capacity
	- Perform data analysis on top of DynamoDB
	- Retain snapshots for auditing
	- ETL on top of S3 data before importing back into DynamoDB
	- Export in DynamoDB JSON or ION format
- Import from S3
	- Import CSV, DynamoDB JSON or ION format
	- Doesn't consume any write capacity
	- Creates a new table
	- Import errors are loggin in [[CloudWatch]] Logs

