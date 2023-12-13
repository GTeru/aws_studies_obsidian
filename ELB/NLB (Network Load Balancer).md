- [[ELB (Elastic Load Balancer)]] that handles layer 4 traffic:
- Forwards TCP & UDP traffic to instances
- Handle millions of requests/s (high performance)
- Less latency ~100ms (vs 400ms in [[ALB (Application Load Balancer)]])
- NLB has __one static IP per [[AZ (Availability Zone)]]__ and supports assigning Elastic IP (helpful for whitelisting specific IPs)
- Not included in AWS free tier

## Target Groups
---
- [[EC2 (Elastic Compute Cloud)]] instances
- IP addresses - private IPs (if you want to redirect to private serves that you own)
- Application Load Balancers if you want to whitelist an IP using NLB and then redirect that traffic using ALB rules
- Health checks support TCP, HTTP and HTTPS protocols
