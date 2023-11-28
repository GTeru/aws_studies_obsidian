Read replicas are used when read requests comes from the application, this makes the application more performatic when requesting reads from the databases since the read replicas handle these requests and the main database handles writes.
The replication process is made __asynchronously__, so the reads are eventually consistent, this depends on the amount of read replicas, write requests, etc...
- Up to 15 Read Replicas
- Within [[Availability Zone (AZs)]], Cross-AZ or Cross [[AWS Region]]
- Replicas can be promoted to their own DB

## Network Costs
---
- For RDS Read Replicas within the same region, you don't pay cross-AZ data transfer
- For read replicas Cross-Region, there's a fee