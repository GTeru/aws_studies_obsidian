- AWS storage services are proprietary technology (unlike [[EFS (Elastic File System)]]/NFS), so to expose data from these services in on-premises you can use Storage Gateway
- AWS is pushing for "hybrid cloud": Part of your infrastructure is on cloud and the other is on-premises
	- This can be due to
			- Long cloud migrations 
		- Security requirements
		- Compliance requirements
		- IT strategy
- Use cases
	- Disaster recovery
	- Backup & Restore
	- Tiered storage
	- On-premises cache & low-latency files acess
- Types of Storage Gateway
	- [[S3 (Simple Storage Service)]] File Gateway
	- [[Amazon FSx]] File Gateway
	- Volume Gateway
	- Tape Gateway
## S3 File Gateway 
---
- Support all S3 [[S3 Storage Classes]], __except__ Glacier
- Extends Application Server NFS or SMB file system via the Storage Gateway, which makes HTTPS requests to the bucket
- Transition to Glacier using [[S3 Lifecycle Policies]]
- Most recently used data is cached in the file gateway
- Bucket access using [[IAM]] role for each File Gateway
- SMB Protocol has integration with Active Directory (AD) for user authentication

## FSx File Gateway
---
- Native access to Amazon FSx for Windows File Server
- Local cache for frequently accessed data
- Windows native compatibility (SMB, NTFS, Active Directory, etc...)
- Useful for group file shares and home directories

## Volume Gateway
---
- Block storage using iSCSI protocol backed by S3
- Backed by [[EBS (Elastic Block Storage)]] snapshots which can help restore on-premises volumes
- Cached volumes: low latency access to most recent data
- Stored volumes: entire dataset is on premise, scheduled backups to S3

## Tape Gateway
---
- Some companies have backup processes using physical tapes
- With Tape Gateway, companies can use the same process but in the cloud
- Virtual Tape Library (VTL) backed by Amazon S3 and Glacier
- Backup data using existing tape-based processes (and iSCSI interface)
- Works with leading backup software vendors

## Hardware Appliance
---
- Using storage gateway means you need on-premises virtualization
- Otherwise you can use a __Storage Gateway Hardware Appliance__
- Can be bought in [Amazon](https://amazon.com)
- Works with File, Volume and Tape Gateways
- Has the required CPU, memory, network, SSD cache resources
- Helpful for daily NFS backups in small data centers
