This is an [[S3]] mechanism used to automate taskes depending on triggers

- Enables integrations with other AWS services, such as [[SNS]], [[SQS]], [[Lambda]]
- Notifications are typically delivered within seconds, but can sometimes take a minute or longer
- Use cases
	- Generating thumbnails of images uploaded to a bucket
	- Notificate when objects are removed from a bucket

## Permissions
---
When you're integrating with other services, you need to attach [[IAM]] permissions to the bucket

## S3 and Amazon EventBridge
---
There's another integration that is super usefull with [[AWS EventBridge]], which you can create triggers to other services from a single S3 event.

- EventBridge rules can trigger actions in over 18 AWS Services
- Advanced filtering options with JSON rules (object metada, size, name, etc...)
- EventBridge Capabilities - Archive, Replay Events Reliable delivery 