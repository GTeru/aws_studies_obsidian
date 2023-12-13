- Cross account
	- Attaching a resource-based policy to a resource (example: [[S3]] bucket policy)
		- When assuming a role (user, application or service) you give up your original permissions and take the permissions assigned to the role
		- Supported by various AWS Services
	- OR using a role as a proxy
		- When using a resource-based policy, the principal doesn't have to give up his permissions

## [[AWS EventBridge]] - Security
---
When an EventBridge rule runs, it needs permissions on the target, each service either needs an resource-based policy or a [[IAM]] role:
- Resource-based policy
	- [[AWS Lambda]]
	- [[SNS (Simple Notification Service)]]
	- [[SQS (Simple Queue Service)]]
	- [[CloudWatch Logs]]
	- [[API Gateway]]
	- etc...
- IAM role
	- [[Kinesis Data Streams]]
	- System Manager Run Command
	- [[ECS (Elastic Container Service)]] task
	- etc...