- Log groups: arbitrary name, usually representing an application
- Log stream: instance within application / log files / container
- Can define log expiration policies (never expire, 1 to 10 years, etc...)
- Logs destinations 
	- [[S3]] (exports)
	- [[Kinesis Data Streams]]
	- [[Kinesis Data Firehose]]
	- [[AWS Lambda]]
	- [[OpenSearch]]
- Logs are encrypted by default
- Can setup KMS-based encryption with your own keys

## Sources
---
- SKD, [[CloudWatch Agent]], CloudWatch Unified Agent
- [[Elastic Beanstalk (EB)]]: collection of logs from application
- [[Elastic Container Service (ECS)]]: collection of logs from containers
- [[AWS Lambda]] collection from function logs
- [[VPC]] Flow Logs: VPC specific logs
- [[API Gateway]]
- [[CloudTrail]]: based on filter
- [[Route53]]: log DNS queries

## Insights
---
- Query feature for CloudWatch logs (filtering by logtype, date, etc...)
- Provides a purpose-built query language
	- Automatically discovers fields from AWS services and JSON log events
	- Fetch desired event fields, filter based on conditions, calculate aggregate statistics, sort events, limit number of events, etc...
	- Can save queries and add them to CloudWatch Dashboards
- Can query multiple Log Groups in different AWS accounts
- It's a query engine, not a real-time engine

## S3 Export
---
- Log data can take up to 12 hours to become available to export
- The API call is CreateExportTask
- Not neal-real time, if real-time is needed, use __Logs Subscriptions__ instead

## Logs Subscriptions
---
- Get real-time log events from CloudWatch Logs for processing and analysis
- Send to Kinesis Data Stream, Firehose or Lambda
- Subscription filter - filter which logs are events delivered to your destination
- Enables log aggreggation on multi-[[AWS Region]] and multi-account
	- Cross Account Subscription - send log events to resources in a different AWS account