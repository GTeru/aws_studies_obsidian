[[CloudFront]] distributions have a cache which has an TTL (Time to Live) to avoid requesting contents from it's origins all the time, especially when you're using it along a [[S3 (Simple Storage Service)]] bucket.
Sometimes if you need to change a content and the cache needs to be invalidated to serve the updated content, this is where Cache Invalidation can help, forcing the distribution to request the contents from its origin again.

- You can invalidate all files (\*) or a special path (/images/\*)
