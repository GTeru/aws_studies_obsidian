- When you create an encrypted [[EBS (Elastic Block Storage)]] volume, you get the following:
	- Data at rest is encryted inside the volume
	- All the data in flight moving between the instance and the volume is encrypted
	- All snapshots are encrypted
	- All volumes created from the snapshot
- Encryption and decryption are handled transparently (you don't have to do anything)
- Encryption has a minimal impact on latency
- EBS Encryption leverages keys from [[KMS (Key Management Service)]] (AES-256)
- Copying an unencrypted snapshot allows encryption
- Snapshots of encrypted volumes are encrypted

## Encrypting an EBS volume
---
- Create an EBS snapshot of the volume 
- Encrypt the EBS snapshot (using copy)
- Create a new EBS volume from snapshot (the volume will also be encrypted)
- Now you can attach the encrypted volume to the original instance