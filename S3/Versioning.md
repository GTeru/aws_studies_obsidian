[[S3]] versioning is used to version the objects in the bucket

- Enabled at the __bucket level__
- Uploads to a same Key (overwrites) changes the version of the object
- It is best practice to version the buckets
	- Protects against unintended deletes (ability to restore a version)
	- Easy to rollback to a previous version
- Notes
	- Any objects not versioned prior to enabling the versioning will have version "null"
	- Suspending versioning does not delete the previous versions
