- CRR - Cross Region Replication ([[AWS Region]])
- SRR - Same Region Replication
- Must enable [[S3 Versioning]] on both source and destionation buckets
- Copying is made asynchronously
- Buckets can be on different AWS Accounts
	- Must give proper [[IAM]] permissions to S3
- After you enable Replication, only new objects are replicated
	- Optionally, you can replicate existing objects using __S3 Batch Replication__
		- Replicates existing objects and objects that failed replication
- For DELETE operations
	- Can replicate delete markers from source to target (optional setting)
	- Deletions with a version ID are not replicated (to avoid malicious deletes)
- There's no chaining of replication
	- If bucket 1 has replication to bucket 2, which has replication to bucket 3, then objects created in bucket 1 won't be replicated to  bucket 3.


## Use Cases
---
- CRR --> compliance, lower latency access, replication across accounts
- SRR --> log aggregation, live replication between production and test accounts

