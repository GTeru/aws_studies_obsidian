## Encryption
---
[[RDS (Relational Database Service)]] && [[Amazon Aurora]] provides some options to encrypt data
- At-rest encryption
	- Database mater & replicas encryption using AWS [[KMS (Key Management Service)]] - must be defined at launch time
	- If master is not encrypted, the read replicas cannot be encrypted
	- To encrypted an un-encrypted database, go through a DB snapshot & restore as encrypted
- In flight encryption (between server and client)
	- TLS-ready by default, use the AWS TLS root certificates client-side

## Authentication
---
- IAM Authentication: [[IAM]] roles to connect to your database (instead of username/password)
- [[Security Group]] Control network access to RDS/Aurora
- No SSH available except on [[RDS Custom]]
- Audit logs can be enabled and sent to [[CloudWatch]] for longer retention