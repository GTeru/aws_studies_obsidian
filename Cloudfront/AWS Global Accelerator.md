Global Accelerator is another kind of performance optimizer of the application, it leverages the AWS internal network by connecting to Edge Locations and server hopping the traffic through AWS internal network.

## Unicast vs. Anycast
---
Global Accelerator uses the concept of Anycast to make it's connections to Edge Locations

- Unicast
	- Each server holds one IP address
- Anycast 
	- All servers hold the same IP address and the client is routed to the nearest one

## Attributes
---
- 2 Anycast IPs are created for your application
- Anycast IP sends traffic directly to Edge Locations
- Edge Locations sends traffic to application

- Works with [[EC2 (Elastic Compute Cloud)]] Elastic IPs, [[Application Load Balancer (ALB)]], [[Network Load Balancer (NLB)]]
- Can be public or private
- Consistent performance
	- Intelligent routing to lowest latency and fast regional failover
	- No issue with client IP cache (because the IP doesn't change)
	- Internal AWS network
- Health Checks
	- Performs health checks of your applications
	- Helps make your application global (failover less than 1 minute for unhealthy intstances)
	- Great for disaster recovery
- Security
	- only 2 external IP need to be whitelisted
	- DDoS protection thanks to [[AWS Shield]]

## Global Accelerator vs [[CloudFront]]
---
- Both uses the AWS global network and Edge Locations around the world
- Both services integrate with AWS Shield for DDoS protection

- CloudFront
	- Improves performance for both cacheable content (such as image and videos)
	- Dynamic content (such as API acceleration and dynamic site delivery)
	- Content served at the edge location
- Global Accelerator
	- Improves performance for a wide applications over TCP or UDP
	- Proxying packets at the edge locations to applications running in one or more [[AWS Region]]
	- Good fit for non-HTTP use cases, such as gaming (UDP), IoT(MQTT) or Voice over IP
	- Good for HTTP use cases that require static IP addresses
	- Good for HTTP that requires deterministic, fast regional failover