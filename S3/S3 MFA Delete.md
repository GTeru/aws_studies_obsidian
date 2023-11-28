Forcing MFA before doing important/risky operations on [[S3]] buckets

- MFA will be required to
	- Permanently delete an object version
	- Suspend [[S3 Versioning]] on the bucket
- MFA won't be required to
	- Enable Versioning 
	- List deleted versions
- Versioning must be enabled on the bucket
- Only the bucket owner (root account) can enable/disable MFA *Delete*