- By default, no logs from your [[EC2 (Elastic Compute Cloud)]] will go to [[CloudWatch]]
- You need to run a CloudWatch agent on EC2 to push the log files you want
- Make sure [[IAM]] permissions are correct
- CloudWatch agent can be setup on-premises too

## Logs Agent & Unified Agent
---
- Used on virtual servers (EC2, on-premise server, etc...)

|Logs Agent|Unified Agent|
|---|---|
|Old version of the agent| Collect additional system-level metrics such as RAM, processes, etc...|
|Can only send to [[CloudWatch Logs]]|Collect logs to send to CloudWatch Logs|
||Centralized configuration using SSM Parameter Store|

## Unified Agent - Metrics
---
- Collect directly on your Linux server / EC2 instance
- CPU (active, guest, idle, system, user, steal)
- Disk Metrics (free, used, total), Disk IO (writes, reads, bytes, iops)
- Netstat (number of TCP and UDP connections, net packets, bytes)
- Processes (total, dead, blocked, idle, running, sleep)
- Swap Space (free, used, used %)
__Reminder__: out of the box metric for EC2 - disk, CPU, network (high level)