[[S3 (Simple Storage Service)]] can host websites and have them accessible on the Internet
- The website URL will have one of these formats (which depends on the region they're in)
	- http://bucket-name.s3-website-aws-region.amazonaws.com
	- http://bucket-name.s3-website.aws-region.amazonaws.com

- If you get a __403 Forbidden__ error, make sure the bucket policy allows public reads
