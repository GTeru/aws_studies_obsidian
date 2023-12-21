Locks prevents [[S3 (Simple Storage Service)]] bucket objects from being deleted/updated after creation. It follows the WORM (Write Once, Read Many) model
## Glacier Vault Lock
---
- Create a Vault Lock Policy
- Lock the policy for future edits (can no longer de changed or deleted) by __anyone__
- Helpful for compliance and data retention

## Object Lock
---
- [[S3 Versioning]] must be enabled
- Block object version deletion for a __specified__ amount of time
- Retention modes
	- Compliance
		- Objects version can't be overwritten or deleted by any user, including the root user
		- Objects retention can't be changed and retention periods can't be shortened
	- Governance
		- Most users can't overwrite or delete an object versionor alter it''s lock settings
		- Some users have a special permission to change the retention or delete the object
- Retentin period
	- Protect the object for a fixed period which can be extended
- Legal hold
	- Protect the object indefinitely, independent from retention period
	- Can be freely placed and removed using the `s3:PutObjectLegalHold` [[IAM]] permission