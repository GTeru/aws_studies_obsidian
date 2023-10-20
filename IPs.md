- AWS has support for both IPv4 and IPv6
## Private IPs
---
- IPs in the same network
- The machine can only be identified on a private network
- The IP must be unique across the private network
- Two different networks can have the same IPs
- Machines are connected to the web using an internet gateway (a proxy)
- Only specific ranges of IPs can be used as private IP
## Public IPs
---
- IPs that are mapped in the WWW
- Must be unique across the whoe web (or else two machines would have the same identifier)
## Elastic IPs
---
- It's a public IPv4 you own as long as you don't delete it
- If you need to have a fixed IP for your instance, you need an Elastic IP
- When you stop and then start an EC2 instance, it can change its public IP.
- By default, it's limited by 5 per account (but you can ask AWS to increase this limit)
- Overall, try to avoid using Elastic IP
	- They often reflect poor architectural decisions
	- Instead, use a random public IP and register a DNS name to it
	- Or, use a Load Balancer and don't use a public IP
- By default [[EC2 (Elastic Compute Cloud)]] instances comes with:
	- A private IP for internal AWS Network
	- A public IP for the web
When using SSH to log into the instance, we use the public IP, and since this it's a public IP, when the machine is restarted it's public __changes__