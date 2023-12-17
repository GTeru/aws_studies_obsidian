## Invoke Lambda from within RDS/Aurora
---
- Invoke [[AWS Lambda]] functions from within your DB instance
- Allows you to process data events from within a database
- Supported for [[RDS (Relational Database Service)]] for PostgreSQL and [[Amazon Aurora]] MySQL
- Must allow outbound traffic to your Lambda function from within your DB instance (Public, NAT GW, [[VPC (Virtual Private Cloud)]] Endpoints)
- DB instance must have the required permissions to invoke the Lambda function (Lambda Resource-based Policy and [[IAM]] Policy)

## RDS Event Notifications
---
- Notifications that tells information about the DB instance itself (created, stopped, started, etc...)
- Don't have any info about data within DB
- Subscribe to the following event categories
	- DB instance
	- DB snapshot
	- DB Parameter Group
	- DB Security Group
	- RDS Proxy
	- Custom Engine Version
- Near real-time events (up to 5 minutes)
- Send notifications to [[SNS (Simple Notification Service)]] or subscribe to events using [[AWS EventBridge]]