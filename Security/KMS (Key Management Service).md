---
tags:
  - Security
---
- Anytime you hear "encryption" for an AWS service, it's most likely KMS
- AWS manages encryption keys for us
- Keys are scoped in a [[AWS Region]]
- Fully integrated with [[IAM]] for authorization
- Easy way to control access to your data
- Able to audit KMS Key usage using [[CloudTrail]]
- Seamlessly integrated into most AWS services 
- Never store secrets in plaintext, especially in code
	- KMS Key Encryption also available through API calls (SDK, CLI)
	- Encrypted secrets can be stores in the code / environment variables

## KMS Keys Encryption Types
---
- KMS Keys is the new name of KMS Customer _Master_ Key
- Symmetric (AWS-256 keys)
	- Single encryption key that is used to Encrypt and Decrypt
	- AWS services that are integrated with KMS use Symmetric CMKs
	- You never get access to the KMS Key unencrypted (must call KMS API to use)
- Assymetric (RSA & ECC key pairs)
	- Public (Encrypt) and Private Key (Decrypt) pair
	- Used for encrypt/decrypt or sign/verify operations
	- Public key is downloadable, but you can't access the Private Key unencrypted
	- Use case
		- Encryption outside of AWS by users who can't call the KMS API

## Types of KMS Keys
---
- AWS Owned Keys (free): SSE-S3, SSE-SQS, SSE-DDB (default key)
- AWS Managed Key (free): aws/service-name e.g.: `aws/rds` or `aws/ebs`
- Customer managed keys created in KMS: 1$/month
- Customer managed keys imported (must be symmetric key): $1/month
- + pay for API call to KMS ($0.03/10.000 calls)

- Automatic Key rotation
	- AWS managed KMS Key: automatic every 1 year
	- Customer-managed KMS Key (must be enabled): automatic every 1 year
	- Imported KMS Key: only manual rotation possible using alias

## KMS Key Policies
---
- Control access to KMS keys, "similar" to [[S3]] bucket policies
	- Difference: you cannot control access without them
- Default KMS Key Policy
	- Default behavior
	- Complete access to the key to the root user = entire AWS account
- Custom KMS Key Policy
	- Define users, roles that can access the KMS Key
	- Define who can manage the key
	- Useful for cross-account access of your key

## Copying snapshots across regions
---
- Since a KMS key scope is always attached to only one region, you can't use the same KMS key in two regions, so you need to snapshot the encrypted resource (e.g.: a [[EBS (Elastic Block Storage)]] volume) that uses the KMS key A and then ReEncrypt with a KMS key B from the another region and restore the volume.

## Copying Snapshots across accounts
---
1. Create a snapshot, encrypted with your own KMS key (Customer managed key)
2. Attach KMS Key Policy to authorize cross-account access
3. Share the encrypted snapshot
4. (in target) Create a copy of the Snapshot, encrypt it with a KMS Customer Managed Key in your account
5. Create a volume from the snapshot