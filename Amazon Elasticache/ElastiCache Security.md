- [[Amazon ElastiCache]] supports [[IAM]] authentication for Redis
- IAM policies on ElastiCache are only used for AWS API-level security
- Redis AUTH
	- Set a "password/token" when you create a Redis cluster
	- This is an extra level of security for your cache (on top of [[Security Group]])
	- Support SSL in flight encryption
- Memcached
	- Supports SASL-based authentication (advanced) 

## Patterns for ElasticCache
---
- Lazy loading: all read data is cached, data can become stale in cache
- Write through: Adds or update data in the cache when written to a DB (no stale data)
- Session store: store temp session data in a cache (using TTL features)

## Redis UseCase
---
- Gaming leaderboards are computationally complex
	- [__Redis Sorted__](https://redis.io/docs/data-types/sorted-sets/) sets__ guarantee both uniqueness and element ordering
	- Each time a new element is added, it's ranked in real time, then added in correct order