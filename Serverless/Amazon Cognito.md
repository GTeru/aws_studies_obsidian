- Give user an identity to interact with web or mobile application
- Cognito User Pool
	- Sign in functionality for app users
	- Integrate with API Gateway & Application Load Balancer

- Cognito Identity Pools (Federated Identity)
	- Provide AWS credentials to users so they can access AWS resources directly
	- Integrate with Cognito User Pools as an identity provider
- Cognito vs [[IAM]]
	- Hundreds of users
	- Mobile users
	- Authentication with SAML

## Cognito User Pools (CUP)
---
- Serverless DB of user for web & mobile apps
- Simple login: username (or email) + password combination
- Password reset
- Email & Phone Number verification
- Multi-factor authentication (MFA)
- Federated identities: users from Meta, Google, SAML, etc...
- CUP integrates with [[API Gateway]] and [[ALB (Application Load Balancer)]]

## Cognito Identity Pools (Federated Identities)
---
- Get identities for "users" so they obtain temporary AWS credentials
- User source can be Cognito User Pools, 3rd party logins, etc...
	- Users can then access AWS services directly or through API Gateway
- [[IAM]] policies applied to credentials are defined in Cognito
- Can be customized based on the user_id for fine grained control
- Default IAM roles for authenticated and gues users
