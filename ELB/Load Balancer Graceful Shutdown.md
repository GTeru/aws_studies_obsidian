- Feature naming
	- Connection Draining - for CLB
	- Deregisteration Delay - for [[ALB (Application Load Balancer)]] & [[NLB (Network Load Balancer)]]
- Time to complete requests while the instance is de-registering or is unhealthy
- Stops sending requests to the [[EC2 (Elastic Compute Cloud)]] instances which is de-registering
- Between 1 to 3600 seconds (default: 300 seconds)
- Can be disabled (setting the value to 0)

### Best practices
---
- Set to a low value if the requests are short
