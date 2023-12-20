---
tags:
  - Management
---
- Allows you to start a secure shell on your [[EC2 (Elastic Compute Cloud)]] instances and on-premises servers
- No SSH access, [[Bastion Hosts]], or  SSH keys needed
- No port 22 needed (better security)
- Supports Linux, macOS and Windows
- Send session log data to [[S3]] and [[CloudWatch Logs]]

## Run Command
---
- Execute a document (= scripts) or just run a command
- Run command across multiple instances (using resource groups)
- Command Output can be shown in the AWS console, sent to S3 bucket or CloudWatch Logs
- Send notififcations to [[SNS (Simple Notification Service)]] status (in progress, success, failed, etc...)
- Integrated with [[IAM]] & [[CloudTrail]]
- Can be invoked using [[AWS EventBridge]]

## Patch Manager
---
- Automates the process of patching managed instances
- OS, applications, security updates
- Supports EC2 instances and on-premises servers
- Supports Linux, macOS and Windows
- Patch on-demand or on a schedule using __Maintenance Windows__
- Scan instances and generate patch compliance report (missing patches)

## Maintenance Windows
---
- Defined a schedule for when to perform actions on your instances
- Example
	- OS patching, updating drivers, installing software, etc...
- Maintenance Window contains
	- Schedule
	- Duration
	- Set of registered instances and tasks

## Automation
---
- Simplifies common maintenance and deployment tasks of EC2 instances and other AWS resources
- Example
	- Restart instances
	- Create an [[AMI (Amazon Machine Image)]]
	- [[EBS (Elastic Block Storage)]] snapshots
- __Automation Runbook__ - SSM document to define actions performed on your EC2 instances or AWS resources (pre-defined or custom)
- Can be triggered using
	- Manually using AWS console, AWS CLI or SDK
	- Amazon EventBridge
	- On a schedule using Maintenance Windows
	- By [[AWS Config]] for rules remediation