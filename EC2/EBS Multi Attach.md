By default, an [[Elastic Block Storage (EBS)]] can only be attached to one [[EC2 (Elastic Compute Cloud)]] instance, but some [[EBS Volume Types]] are able to attach to multiple instances:
- Available for io1/io2 family of [[EBS Volume Types]]
- Each instance has full read & write permissions to the high-performance volume
- Use case:
	- Achieve higher application availability in clustered Linux applications (ex: Teradata)
	- Applications must manage concurrent write operations
- Is available only to instances in the same [[Availability Zone (AZs)]]
- Up to 16 EC2 instances at a time
- Must use a file system that's cluster-aware (not XFS, EXT4, etc...)