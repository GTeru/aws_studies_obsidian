- Move large amount of data to and from
	- On-premises / other cloud to AWS (NFS, SMB, HDFS, [[S3 (Simple Storage Service)]] API, etc...) - needs agent like Snowcone from [[AWS Snow Family]]
	- AWS to AWS (different storage services) - no agent needed
- Can synchronize to
	- S3 (any storage classes)
	- [[EFS (Elastic File System)]]
	- [[Amazon FSx]]
- Replication tasks can be scheduled hourly, daily, weekly
- File permissions and metadata are preserved (NFS POSIX, SMB, etc...)
- One agent task can use 10GBps, can customize bandwidth limit
