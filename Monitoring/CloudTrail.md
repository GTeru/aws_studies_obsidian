---
tags:
  - Monitoring
---
- Provides governance, compliand and audit for your AWS Account
- CloudTrail is enabled by default
- Get an history of events / API calls made within your AWS Account by
	- Console
	- SDK
	- CLI
	- AWS Services
- Can put logs from CloudTrail into [[CloudWatch Logs]] or [[S3]]
- A trail can be applied to All [[AWS Region]] (default) or a single Region
- If a resource is deleted in AWS, investigate CloudTrail first!

## Events
---
1. Management Events
	- Operations that are performed on resources in your AWS account
	- Examples
		- Configuring security ([[IAM]] AttachRolePolicy)
		- Configuring rules for routing data ([[EC2 (Elastic Compute Cloud)]])
	- By default, trails are configured to log management events
	- Can separate __Read Events__ (that don't modify resources) from __Write Events__ (that modify resources)
2. Data Events
	- By default, data events are not logged (because of high operation volume)
	- Write and Read Events can be separated
	- [[AWS Lambda]] function execution activity
3. CloudTrail Insigh Events
	-  Disabled by default
	- It can identify anomalies in your account activity
		- Innacurate resource provisioning
		- Hitting service limits
		- Bursts of AWS IAM actions
		- Gaps in periodic maintenance activity
	- CloudTrail Insights analyzes normal management events to create a baseline
	- And then continuously analyzes write events to detect unusual patterns
		- Anomalies appear in the CloudTrail console
		- Event is sent to Amazon S3
		- An [[AWS EventBridge]] event is generated (for automation needs)

## Event Retention
---
- Events are stored for 90 days
- To keep events beyond this period, log them to S3 and use [[Athena]]