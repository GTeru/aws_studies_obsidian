Users given a pre-signed URL inherit the permissions of the user that generated the URL for GET/PUT to a [[S3]] file without making the object public

- Generate pre-signed URLs using the S3 Console, AWS CLI or SDK
- URL Expiration
	- S3 Console: 1min up to 720minutes (12hours)
	- AWS CLI - configure expiratio with `--expire-in` parameter in seconds (defaults 3600seconds, max 604.800 seconds which is aorund 168 hours )

## Use Cases
---
- Allow only logged-in users to download a premium video from your S3 bucket
- Allow an ever-changing list of users to download files by generating URLs dynamically
- Allow temporarily a user to upload a file to a precise location in your S3 bucket