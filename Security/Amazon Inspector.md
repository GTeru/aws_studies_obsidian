---
tags:
  - Security
---
- Automated Security Assessments
- For [[EC2 (Elastic Compute Cloud)]] instances
	- Leverage AWS System Manager (SSM) agent
	- Analyze against unintended network accessibility
	- Analyze the running OS against known vulnerabilities
- For container images pushed to [[ECR (Elastic Container Registry)]]
	- Assessment of Container Images as they are pushed
- For [[AWS Lambda]]
	- Identifies software vulnerabilities in function code and package dependencies
	- Assessment of functions as they are deployed
- Reporting & integration with AWS Security Hub
- Send findings to [[AWS EventBridge]]

## What is evaluated?
---
- Continuous scanning of the infrastructure
- Package vulnerabilities (EC2, ECR & Lambda) - [CVE](https://www.cve.org/) database
- Network reachability (EC2)
- A risk score is associated with all vulnerabilities for priorization