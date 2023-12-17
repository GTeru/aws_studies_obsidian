---
tags:
  - Network
---
- [[AWS Lambda]] + API Gateway: No infrastructure to manage
- Support for WebSocket Protocol
- Handle API versioning (v1, v2, etc...)
- Handle different environments (dev, test, prod, etc...)
- Handle security (Authentication and Authorization)
- Create API keys, handle request throttling
- Swagger / OpenAPI import to quickly define APIs
- Transform and validate requests and responses
- Generate SDK and API specifications
- Cache API responses

## Integrations High Level
---
- Lambda Function
	- Invoke Lambda Function
	- Easy way to export REST API backed by AWS Lambda
- HTTP
	- Expose HTTP endpoints in the backend
	- Example
		- Internal HTTP API on premise
		- [[ALB (Application Load Balancer)]]
	- Why? Add rate limiting, caching, user authentications, API keys, etc...
- AWS Service
	- Expose any AWS API through the API Gateway
	- Example
		- Start an [[Step Function]] workflow
		- Post a message to [[SQS (Simple Queue Service)]]
	- Why? Add authentication, deploy publicly, rate control, etc...

## Security
---
- User authentication through
	- [[IAM]] roles (useful for internal applications)
	- [[Amazon Cognito]] (identity for external users - example mobile users)
	- Custom Authorizer (your own logic)
- Custom Domain Name HTTPS security through integration with [[ACM (Amazon Certificate Manager)]]
	- If using Edge-Optimizd endpoint, then the certificate must be in __us-east-1__
	- If using Regional endpoint, the ceritifcate must be in the API Gateway region
	- Must setup CNAME or A-alias record in [[Route53]]