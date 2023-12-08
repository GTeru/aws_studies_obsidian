---
tags:
  - Network
---
- It's a type of [[ELB (Elastic Load Balancer)]] which acts on layer 7 of the [OSI model](https://en.wikipedia.org/wiki/Application_layer) (e.g. HTTP)
- It's capable of load balancing to multiple HTTP applications across machines, which are called __target groups__
- Also possible to load balance to multiple applications on the same machine (ex. different containers in the same machine)
- Support for [HTTP/2](https://developer.mozilla.org/en-US/docs/Glossary/HTTP_2) and [WebSocket](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
- Supports redirects (from HTTP to HTTPS for example)
- Routing tables to different __target groups__:
	- Routing based on path in URL
	- Routing based on hostname in URL
	- Routing based on Query Strings and Headers
- ALB are great fit for micro services & container-based application (example: Docker & Amazon ECS)
- Has port mapping feature to redirect to a dynamic port in ECS
- In comparison, we'd need multiple Classic Load Balancer per application

## Target Groups
---
- EC2 instances (can be managed by an Auto Scaling Group) - HTTP
- ECS tasks (managed by ECS itself) - HTTP
- Lambda functions - HTTP request is translated into a JSON event
- IP Addresses - must be private IPs
- ALB can route to multiple target groups
- Health checks are at the target group level
- Fixed hostname
- The application servers don't see the IP fo the client directly
	- True IP of the client is inserted in the header __X-Forwarded-For__
	- We can also get the Port (__X-Forwarded-Port__) and Protocol (__X-Forwarded-Proto__)

