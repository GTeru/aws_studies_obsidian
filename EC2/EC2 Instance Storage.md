---
tags:
  - Storage
---
Usually [[EBS (Elastic Block Storage)]] have more latency because they're a __network drive__ that connects to the [[EC2 (Elastic Compute Cloud)]] instance, but there's another storage option that solves this problem, it's called an EC2 Instance Store, which is a __hardware disk__ that is directly attached to the instance physical server.
- __Pros__
	- Better I/O performance
- __Cons__
	- EC2 Instance Store lose their storage if they're stopped (ephemeral)
	- Risk of data loss if hardware fails
	- Backups and Replication are your responsability
- Use case: buffer/ cache / scratch data/ temporary content