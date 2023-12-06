## KDA for SQL Application
---
- Real time analytics on [[Kinesis Data Streams]] and [[Kinesis Data Firehose]] using SQL
- Add reference from [[S3]] to enrich streaming data
- Fully managed, no servers to provision
- Automatic scaling
- Pay for actual consumption rate
- Output
	- Kinesis Data Streams: create streams out of real-time analytics queries
	- Kinesis Data Firehose: send analytics query results to destinations
- Use cases
	- Time-series analytics
	- Real-time dashboards
	- Real-time metrics

## Amazon Managed Service (KDA) for Apache Flink
---
- Use Flink (Java, Scala or SQL) to process and analyze data streaming data
- Run any [Apache Flink](https://flink.apache.org/) application on a managed cluster on AWS
	- Provisioning compute resources, parallel computation, automatic scaling
	- Application backups (implemented as checkpoints and snapshots)
	- Use any Apache Flink programming features
	- Flink does no read from Firehose (use Kinesis Analytics for SQL instead)