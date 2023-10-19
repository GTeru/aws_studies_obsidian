IAM (Identity and Access Management) controls AWS accesses and management of identity 

It touches every AWS Service, AWS has a policy (no pun intended) of giving minimal control and access to users and services, so it's a rule of thumb that whenever we're using a new AWS Service, we'll probably have to configure some kind of IAM "setting"

## Key Concepts
---
1. User - users that have different kind of accesses to AWS Services and that are able to have different actions.
2. Policies - Policies are a JSON formatted document that grants capabilities that can be attached to both Users and Roles and they provide different capabilities and power to user and roles (e.g.: being able to list s3 files, delete files, etc... ).
   **Example Policy**
	```json
	{
		"Version": "2012-10-17",
		"Statement": [
			{
				"Effect": "Allow",
				"Action": "logs:CreateLogGroup",
				"Resource": "arn:aws:logs:sa-east-1:236957026736:*"
			},
			{
				"Effect": "Allow",
				"Action": [
					"logs:CreateLogStream",
					"logs:PutLogEvents"
				],
				"Resource": [
					"arn:aws:logs:sa-east-1:236957026736:log group:/aws/lambda/spotify_discover:*"
				]
			}
		]
	}
   ```
3.  User Groups - They're group of users that have 1 or more policies attached to them, they're a simple way to group users by capabilities and responsabilities inside your AWS account (maybe you'd like to have users that have admin access and another group that only manages AWS Lambda services).
4. Roles - Roles are similar to users, but they're attached to AWS Services (imagine we have a Lambda function that needs to do some image processing and upload the resulting image into a s3 bucket, the lambda function would need to have access to s3 to make this operation)
5. Identity Providers
## Services
---
- User MFA (multi-factor authentication)
- SDK (Software development kit) - Used for applications to have AWS Services capabilities, such as boto3 for python applications or even the AWS CLI mentioned in [[Managing AWS (User)]]

IAM has a focus on giving minimal accesses and capabilities to users and services, but it can be difficult remember and lose track of all the users, roles and policies created, so IAM provides two services that helps manage IAM objects:

1. IAM Credentials Report (account-level): Lists all account's users and status of their credentials
2. IAM Access Advisor (user-level): Show the service permissions granted to a user and when they were last accessed. Can also use this service to review policies and accesses.

## Best Practices
---
- Don't use the `root` account except for AWS account setup
- One physical user = One AWS user
- Assign `Users` to `Groups` and assign `Permissions` to groups (avoid custom permissions because it can make it difficult to track it)
-  Create a strong password policy
- Use and enforce the use of `MFA`
- Create and use `Roles` for giving permissions to AWS services such as `EC2` and `Lambda`
- Use Access Keys for programmatic access  such as CLI or SDK
- Audit permissions of your account using `IAM Credentials Report` & `IAM Access Advisor`