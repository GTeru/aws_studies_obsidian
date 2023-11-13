- Highly available, scalable, fully managed and _Authoritative_ [[DNS]]
	- Authoritative = customer can update the DNS records
- Route53 is also a Domain Registrar
- Ability to check the health of your resorces
- Only AWS service which provides 100% availability SLA
- 53 is a reference to the commonly used port for DNS 
## Route53 Record
---
- Domain/subdomain name -> e.g. example.com
- Record Type -> e.g. A or AAAA
- Value -> e.g. 12.34.56.78
- Routing policy -> how Route53 responds to queries
- TTL (Time to Live) -> time the record cached at DNS Resolvers

## DNS Types
---
- (must know) A / AAAA / CNAME / NS
- (advanced) CAA / DS/ MX / NAPTR / PTR / SOA / TXT / SPF / SRV

- A -> maps a hostname to IPv4
- AAAA -> maps a hostname to IPv6
- CNAME -> maps a hostname to another hostname
	- The target is a domain name which must have an A or AAAA record
	- Can't create a CNAME record for the top node of a DNS namespace (Zone Apex)
		- Example: can't create for `example.com`, but you can create for `www.example.com`
- NS -> name servers for the hosted zone
	- Control how traffic is routed for a domain

## Hosted Zones
---
A container for records that define how to route traffic to a domain and it's subdomains

- __Public Hosted Zones__ -> contains records that specify how to route traffic on the internet (public domain names)
- __Private Hosted Zones__ -> contain records that specify how route traffic within one or more VPCs (private domain names)
- You pay $0.50 per month per hosted zone

## TTL
---
Time To Live is a value that Route53 sends to the client when a DNS query is made to Route53. It is the time (in seconds) of a cached response for the DNS query. 
This is used to diminish traffic into Route53, consequently decreasing the cost of it (because it's charged by request).

- High TTL
	- less traffic to Route53
	- more difficult to change records
	- records that don't change often
- Low TTL
	- more traffic to Route53
	- easier to change records

Since it's easy to change records, a good strategy to change records is change to a low TTL, wait for all clients to have a lower TTL, change the record and go back to a higher TTL.