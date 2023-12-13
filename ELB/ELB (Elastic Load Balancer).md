---
tags:
  - Network
---
## Load Balancers
---
Load balancer are serves that forward traffic to multiple servers (e.g. [[EC2 (Elastic Compute Cloud)]] instances) downstream.
The load balancer stands in front of the client, so clients that makes the request to an application don't directly connect to an EC2 instance for example, but it connects to a load balancer that forwards it's traffic to the instance.
- Spread load across multiple instances
- Expose single point of access (DNS) to the application
- Seamlessly handle failures of downstream instances
- Do regular health checks to your instances
- Provide SLL termination (HTTPS) for your websites
- Enforce stickiness with cookies
- High availability across [[AZ (Availability Zone)]]
- Separate public traffic from private traffic
 
## ELB
---
- An ELB is a __managed load balancer__
	- AWS guarantees it will be working
	- AWS takes care of upgrades, maintenance, high availability
	- AWS provides only a few configuration knobs

- It costs less to setup your own load balancer but it will be a lot more effort on your end.

- It is integrated with many AWS offerings/services
	- EC2, Auto Scaling Groups, Amazon ECS
	- AWS Certificate Manager (ACM), Cloudwatch
	- Route53, AWS WAF, AWS Global Accelerator

## Health Checks
---
Health checks are a way for the load balancer to check if the instance has is in good condition (healthy) to respond do requests made for it.
- Health check is done on a port and route (_health/_  is a common one)
- If the response is not 200 (OK), then the instance is unhealthy

## Types of Load Balancers
---

| Name | Version | Launch year | Acronym |Protocols| 
|---|---|---|---|---|
|Classic Load Balancer| v1 (old generation, __deprecated__)| 2009 | CLB|HTTP, HTTPS, TCP, SSL|
|Application Load Balancer| v2 (new generation)| 2016| ALB|HTTP, HTTPS, WebSocket|
|Network Load Balancer|v2 (new generation)| 2017| NLB|TCP, TLS(secure TCP), UDP|
|Gateway Load Balancer|| 2020| GWLB| Operates at layer 3 ([Network Layer](https://en.wikipedia.org/wiki/Network_layer)) - IP Protocol|
- Some load balancers can be setup as __internal__ (private) or __external__ (public) ELBs
## Load Balancer Security Groups
---
Clients can connect to load balancers from anywhere, so it needs [[Security Groups]] to be able to have a layer of security and "firewall".

EC2 instances otherwise, would only accept traffic from the load balancer, so it's security group would have a __"Allow traffic only from Load Balancer"__ configuration.