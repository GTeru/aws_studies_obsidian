---
tags:
  - Security
---
- Easy way to set up and govern a secure and compliant _multi-account AWS environment_ based on best practices
- AWS Control Tower used [[AWS Organizations]] to create accounts
- Benefits
	- Automate the set up of your environment in a few clicks
	- Automate ongoing policy management using guardrails
	- Detect policy violations and remediate them
	- Monitor compliance through an interactive dashboard

## Guardrails
---
- Provides ongoing governance for your Control Tower environments (AWS Accounts)
- __Preventive guardrail__ - using SCPs (e.g.: Restrict Regions across all your accounts)
- __Detective guardrail__ using [[AWS Config]] (e.g.: identify untagged resources)