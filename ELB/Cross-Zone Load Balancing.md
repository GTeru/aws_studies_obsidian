This is a configuration that is available for [[ELB (Elastic Load Balancer)]] that are in different [[Availability Zone (AZs)]], there's two configurations possible:
![x_zone_load_balancing.png](./Images/x_zone_load_balancing.png)
## Differences by Load Balancer type
---
- Application Load Balancer
	- Enabled by default (can be disabled at the Target Group Level)
	- No charges for inter [[Availability Zone (AZs)]] data
- [[Network Load Balancer (NLB)]] && [[Gateway Load Balancer (GLB)]]
	- Disabled by default
	- You pay charges for inter [[Availability Zone (AZs)]] data if enabled
- Classic Load Balancer
	- Disabled by default
	- No charges in case X-Zone is enabled