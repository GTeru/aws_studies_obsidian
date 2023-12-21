Access Points simplify security management for [[S3 (Simple Storage Service)]] buckets, attaching a prefix to a generated URL

- Each access point has
	- It's own DNS name (Internet Origin or [[VPC (Virtual Private Cloud)]] Origin)
	- An Access Point Policy (similar to bucket policy) - manage security at scale

## VPC Origin Setup
---
- It's possible to define the access point to be accessible only from within the VPC
- Must create a VPC Endpoint to access the Access Point (Gateway or Interface Endpoint)
- VPC Endpoint Policy must allow access to the target bucket and Access Point

## Object Lambda
---
- Use AWS [[AWS Lambda]] to change the object before it is retrieved by the caller application
- Only one S3 bucket is needed, on top of which we create S3 Access Point and S3 Object Lambda Access Points
- Use Cases
	- Redacting personally identifiable information for analytics or non-production environments
	- Converting across data formats (XML to JSON for example)
	- Resizing and watermarking images on the fly using __caller-specific details__, such as the user who requested the subject