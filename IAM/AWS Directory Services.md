---
tags:
  - Security
---
- What is Microsoft Active Directory (AD)?
	- Found on any Windows Server with AD Domain Services
	- Database of objects: User Accounts, Computers, Printers, File Shares, Security Groups
	- Centralized security management, create account, assign permissions
	- Object are organized in trees
	- A group of trees is a forest
- AWS Directory Services
	- AWS Managed Microsoft AD
		- Create your own AD in AWS, managed users locally, supports MFA
		- Establish "trust"connections with your on-premise AD
	- AD Connector
		- Directory Gateway (proxy) to redirect premise AD, supports MFA
		- Users are managed on the on-premise AD
	- Simple AD
		- AD-compatible managed directory on AWS
		- Cannot be joined with on-premise AD

## AD Setup
---
- Connect to an AWS Managed Microsoft AD (directory service)
	- Integration is out of the box
- Connect to a Self-Managed Directory
	- Create two-way trust relationship using AWS Managed Microsoft AD
	- Create an AD Connector