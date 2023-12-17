 - Serverless query service to analyze data stored in Amazon [[S3]]
 - Uses standard SQL language to query the files (built on Presto)
 - Supports CSV, JSON, ORC, Avro and Parquet
 - Pricing: $5.00 per TB of data scanned
 - Commonly used with [[Amazon QuickSight]] for reporting/dashboards
 - Use cases
	 - Business intelligence
	 - Analytics
	 - Reporting, analyze and query [[VPC (Virtual Private Cloud)]] Flow Logs
	 - [[CloudFront]] trails
	 - etc...

## Performance Improvements
---
- Use __columnar data__ for cost-savings (less scan)
	- Apache Parquet or ORC is recommended
	- Huge performance improvement
	- Use [[AWS Glue]] to convert data to Parquet or ORC
- __Compress data__ for smaller retrievals (bzip2, gzip, lz4, snappy, zlip, zstd, etc...)
- __Partition__ datasets in S3 for easy querying on virtual columns
- Use __larger files__ (> 128Mb) to minimize overhead

## Federated Query
---
- Allows you to run SQL queries across data stored in relational, non-relational, object and custom data sources (AWS or on-premises)
- Uses Data Source Connectors that run on [[AWS Lambda]] to run Federated Queries (e.g.: [[CloudWatch]] Logs, [[DynamoDB]], [[RDS (Relational Database Service)]], etc...)
- Store the results back in S3