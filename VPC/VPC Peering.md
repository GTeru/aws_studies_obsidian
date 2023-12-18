- Privately connect two [[VPC (Virtual Private Cloud)]]s using AWS' network
- Make them begave as if they were in the same network
- Must not have overlapping [[CIDR]]s
- VPC Peering connection is __NOT__ transitive (must establish connection for each VPC that need to communicate with one another)
- Must update [[Route Table]] in _each VPC's [[Subnet]]s_ to ensure [[EC2 (Elastic Compute Cloud)]] instances can communicate with each other

## Good to Know
---
- Create VPC Peering connection between VPC's in different [[AWS Region]] and accounts
- Can reference [[Security Group]] in a peered VPC (works coss accounts - same region) 