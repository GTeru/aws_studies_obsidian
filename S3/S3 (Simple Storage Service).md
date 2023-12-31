---
tags:
  - Storage
  - Serverless
---
Amazon S3 is a "file system" where users are able to store __objects__ (files) into __buckets__ (directories), to create a bucket there are some requirements it needs to solve:
- Buckets must have a globally unique name (across all regions, all accounts)
- Buckets are defined at the region level
- Naming conventions
	- No uppercase and underscore (\_\)
	- 3 - 63 characters long
	- Not an IP
	- Must start with lowercase letter or number
	- Must _NOT_ start with the prefix __xn--__
	- Must _NOT_ end with the suffix __-s3alias__

## Use cases
---
- It's advertised as an _"infinitely scaling"_ storage
- Many websites uses S3 as a backbone
- Many AWS Services use S3 as an integration as well
	- Backup and storage
	- Disaster recovery
	- Archive
	- Hybrid Cloud Storage
	- Application Hosting
	- Media Hosting
	- Data Lakes & Big Data Analytics
	- Software Delivery
	- Static Websites

## S3 Objects (files)
---
- Max object size is 5TB (5000GB)
- If you're uploading a file with more than 5GB, you must upload it using a "multi-part upload" with each part having a maximum size of 5GB
- Objects can have metadata (key/value pairs that can be user or system defined)
- Up to 10 Tags (unicode key/value pair) which are useful for security/object lifecycle
- Version ID (if bucket versioning is enabled)
### Object Keys
Each object has an __Key__ assigned to them, the key is the __FULL PATH__ of the object inside the bucket. 
- In `s3://my-bucket/a_file.txt`, `a_file.txt` is the Key
- In `s3://my-bucket/important_stuff/a_file.txt`, `important_stuff/b_file.txt` is the Key

The key is also compromised of two parts
1. Object name -> the file name
2. Preffix -> what comes before the file name
- In `s3://my-bucket/a_file.txt`, 
	- Preffix: No preffix
	- Object Name: `a_file.txt`
- In `s3://my-bucket/important_stuff/a_file.txt`
	- Preffix: `important_stuff/`
	- Object Name: `b_file.txt`

There's no concept of "directories", but the Key names (and AWS UI) can trick you.
