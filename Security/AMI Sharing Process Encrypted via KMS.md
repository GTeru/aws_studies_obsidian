1. [[AMI (Amazon Machine Image)]] in Source Account in encrypted with [[KMS (Key Management Service)]] Key from Source Account
2. Must modify the image attribute to add a _Launch Permission_ which corresponds to the specified target AWS account
3. Must share the KMS Keys used to encrypt the snapshot of the AMI with the target account / [[IAM]] role
4. IAM role/User in the target account must have the following permissions `DescribeKey`, `ReEncrypted`, `CreateGrant`, `Decrypt`
5. Optionally, the target account can specify a new KMS Key in it's own account to re-encrypt the volumes, when launching an [[EC2 (Elastic Compute Cloud)]] instance from the AMI