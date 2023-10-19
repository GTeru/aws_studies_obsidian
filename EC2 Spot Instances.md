An important type of [[EC2 (Elastic Compute Cloud)]] purchase option that has a very interesting and value proposition.

- It has the most aggressive discount (up to 90%) compared to the On-Demand
- Define max spot price and get the instance while current spot price < max
	- Hourly spot prices varies based on offer and capacity
	- If the current price > max price, the instance will be taken out, you can either stop or terminate the instance before it is taken out with a grace period of 2 minutes.
- Spot block
	- You can also "block" the instance during a specified time frame (1 to 6 hours) without interruptions

## Spot request

Spot instances can be booted via a **spot request**, which can be configured in two ways:
1. One time -  request is made one time and then it is closed
2. Persistent - request is made "continuously", it monitors how many requests are currently running and how many were requested and if running instances< requested instances, it requests a new instance.
Since persistent requests exists, it is important to close the request and then terminate the instances so no new requests are made and consequently new instances are launched.

