- Target tracking scaling
	- Most simple and easy to set-up
	- Example: Average ASG CPU to stay around 40%
- Simple / Step Scaling
	- When a [[CloudWatch]] alarm is triggered (example CPU > 70%), then add 2 units
- Scheduled actions
	- Anticipate a scaling based on know usage patters
	- Example: increase the min capacity to 10 at 5pm on Fridays
- Predictive scaling
	- Continuously (AI-powered) forecast load and schedule scaling ahead

## Metrics
---
- CPU Utilization: Average CPU
- Request count per Target
- Average Network In / Out
- Any custom metric (that uses CloudWatch)

## Scaling Cooldowns
---
- After scaling activity happens, ASG will be on a cooldown period (default 300 seconds)
- Cooldowns are important because they'll let scaling policies metrics stabilize before taking more actions, if the cooldown isn't as effective, ASG could scale-in/out the instances and make the application unstable/unavailable or sky-rocket EC2 instances costs.
- Advice: Use a ready to use [[AMI (Amazon Machine Image)]] to reduce configuration/startup time in order to be serving requests faster and reduce the cooldown period.