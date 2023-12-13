---
tags:
  - Monitoring
---
- Service that helps with auditing and recording compliance of your AWS resources
- Helps record configurations and changes over time
- Examples
	- Unrestricted SSH access to my security groups?
	- Buckets have any public access?
	- How has my ALB configuration changed over time?
- Receive alerts ([[SNS (Simple Notification Service)]] notifications) for any changes
- Can be aggregated across [[AWS Region]] and accounts
- Possibility of storing the configuration data into [[S3]] (analyzed by [[Athena]])

## Config Rules
---
- Can use AWS managed config rules
- Can create custom config rules (must be defined in [[AWS Lambda]])
	- Evaluate if each EBS disk is of type gp2
	- Evaluate if each EC2 instance is t2.micro
- Rules can be evaluated / triggered
	- For each config change
	- Regular time intervals
- AWS Config Rules does not prevent actions from happening
- Pricing: no free tier, $0.003 per configuration item recorded per region, $0.001 per config evaluation per region

## Config Resource
---
- View compliance of a resource over time
- View configuration of a resource over time
- View [[CloudTrail]] API calls of a resource over time

## Remediations
---
- Automate remediation of non-compliant resources using SSM Automation Documents
- Use AWS-Managed Automation Documents or create custom Automation Documents
	- Tip: you can create Automation Documents that invokes Lambda functions
- You can set __Remediation Retries__ if the resource is still non-compliant after auto-remediation

## Notifications
---
- Use [[AWS EventBridge]] to trigger notifications when AWS resources are non-compliant
- Ability to send configuration changes and compliance state notifications to SNS (all events - use SNS Filtering or filter at client-side)