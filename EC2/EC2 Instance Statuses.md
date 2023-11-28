Some general information about [[EC2 (Elastic Compute Cloud)]] instance status.
## Start
---
On start the OS boots and the EC2 User Data script is run
Then the application starts, caches get warmed up and that can take some time.
## Stop
---
Stops the cache, application and OS.
The data on disk (EBS) is kept intact in the next start
## Terminate
---
Any non persistent EBS volumes (root) also set-up to be destroyed 
## Hibernate
---
- The in-memory (RAM) state is preserved
- Instance boots much faster because of that (oS is not stopped/restated)
- Under the hood: RAM state is written to a file in the root EBS volume
- The root EBS volume must be encrypted
- Instance RAM Size - < 150Gb
- Instance size - not supported for bare metal instances
- AMI - Amazon Linux 2, Linux AMI, Ubuntu, RHEL, CentOS & Windows
- Root volume - must be EBS, encrypted, not instance storage and large
- Available for On-Demand, Reserved and Spot instances
- Also, an instance __cannot__ be hibernated more than 60 days.