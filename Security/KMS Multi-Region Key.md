- Identical [[KMS (Key Management Service)]] keys in different [[AWS Region]] that can be used interchangeably
- Multi-region keys have the same key ID, key material, automatic rotation, etc...
- Encrypt in one Region and decrypt in other Regions
- No need to re-encrypt or making cross-region API calls
- KMS Multi-region are not global (primary + replicas)
	- Each multi-region key is managed _independently_
- Use case
	- Global client-side encryption
	- Encryption on Global [[DynamoDB]]
	- Global [[Amazon Aurora]]

## DynamoDB and KMS Multi-region Client-side encryption
---
- We can encrypt specific attributes client-side in our DynamoDB table using the __Amazon DynamoDB Encryption Client__
- Combined with Global Tables, the client-side encrypted data is replicated to other regions
- If we use a multi-region key, replicated in the same region as the DynamoDB Global table, then clients in these regions can use low-latency API calls to KMS in their region to decrypt the data client-side
- Using client-side encryption we can protect specific fields and guarantee only decryption if the client has access to an API key

## Aurora and KMS Multi-region Client-side encryption
---
- We can encrypt specific attributes client-side in our DynamoDB table using the __AWS Encryption SDK__
- Combined with Aurora Global Tables, the client-side encrypted data is replicated to other regions
- If we use a multi-region key, replicated in the same region as the Global Aurora DB, the clients in these region can use low-latency API calls to KMS in their region to decrypt the data client-side
- Using client-side encryption we can protect specific fields and guarantee only decryption if the client has access to an API key