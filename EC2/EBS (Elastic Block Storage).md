---
tags:
  - Storage
---
- It's a network drive that you can attach to your [[EC2 (Elastic Compute Cloud)]] instances while they run
- It allows the instance to persist data, even after termination
- They're also specific to an [[AZ (Availability Zone)]]
- THe analogy is that the EBS is an "network USB stick"
## Attributes
---
- Since it's an network drive that connects to the instance, it has some latency while communicating with it, but it also can be easily moved through instances.
- It's not possible to move EBS though AZs but it's possible create a new one via an snapshot.
- By default, an EBS is deleted on EC2 termination, but tha't configurable
## Snapshots
---
- Used to create a backup of the EBS volume at a point in time
- It's not necessary to detach the volume to do a snapshot, but it's recommended
- The snapshot can be copied to another AZ or Region
### Snapshot Archive
- Move a snapshot to an "archive tier", which is 75% cheaper
- It takes from 24 to 72hrs to restore the archive
### Recycle Bin
- Setup rules to retain deleted snapshots so you can recover them after an accidental deletion
- Retention period from __1 day to 1 year__
### Fast Snapshot Restore (FSR)
- Force full initialization of snapshot to have no latency on the first use, which costs more, of course. 
- Use case: Big volumes attached to the instance