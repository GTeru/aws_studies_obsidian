Both CNAME and Alias maps a hostname to another hostname.
AWS resources (load balancers, cloudfront, etc...) exposes an hostname, you can map this domain name (which is non-human friendly, to a human-friendly hostname), but CNAME and Alias have their own differences.

- CNAME
	- Points a hostname to any other hostname (__app.mydomain.com__ -> __blabla.anything.com__)
	- Only works for __NON-ROOT__ domain (e.g. __something.mydomain.com__)
- Alias:
	- Points a hostname to an AWS resource 
	- Works for both ROOT domain and NON-ROOT domain (e.g. mydomain.com)
	- Free of charge
	- Native health check capabilities

## Alias Records
---
- Maps a hostname to an AWS resource
- An extension to DNS functionality
- Automatically recognizes changes in the resource's IP addresses
- Unlike CNAME, it can be used for the top node of a DNS namespace (name Zone Apex)
- Alias record is always of type A(IPv4) / AAAA(IPv6) for AWS resources
- Can't set TTL

## Alias records targets
---
- [[ELB (Elastic Load Balancer)]]
- [[Cloudfront]]
- API gateway
- [[Elastic Beanstalk (EB)]] environments
- [[S3]] Websites
- VPC Interface Endpoints
- Global Accelerator
- [[Route53]] record in the same hosted zone

- Can't set an ALIAS record for an [[EC2 (Elastic Compute Cloud)]] DNS name