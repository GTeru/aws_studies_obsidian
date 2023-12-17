---
tags:
  - Security
---
- Newer service, meant for storing secrets
- Capability to force _rotation of secrets_ every X days
- Automate generation of secrets on rotation (uses [[AWS Lambda]])
- Integration with [[RDS (Relational Database Service)]] (MySQL, PostgreSQL, [[Amazon Aurora]])
	- Mostly meant for RDS integration
- Secrets are encrypted using [[KMS (Key Management Service)]]

## Multi-[[AWS Region]] Secrets
---
- Replicate secrets across multiple AWS Regions
- Secrets manager keeps read replicas in sync with primary Secret Store
- Ability to promote a read replica Secret to a standalone Secret (Disaster Recovery)
- Use cases
	- Multi-region apps
	- Disaster recovery strategies
	- Multi-region DB