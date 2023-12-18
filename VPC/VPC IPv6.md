- IPv4 designed to provide 4.3 Billion addresses (they'll be exhausted soon)
- IPv6 is the sucessor of IPv4
- Designed to provide $3.4*10^{34}$ unique addresses
- All addresses are public and Internet-routable (no private ranges)
- Format -> `a:b:c:d:e:f:g:h` (each letter is _hexadecimal_, with a range from 0000 to ffff)
- Examples
	- abcd:ef8:3333:4444:5555:6666:7777:8888
	- :: (all 8 segments are zero)
	- 291:db8:: (last 6 segments are zero)
	- ::1234:4567 (first 6 segments are zero)
	- abcd:ef12::1234:5678 (middle 4 segments are zero)

## IPv6 in VPC
---
- IPv4 __cannot__ be disabled for your [[VPC (Virtual Private Cloud)]] and [[Subnet]]
- You can enable IPv6 (they're public IP addresses) to operate in dual-stack mode
- Your [[EC2 (Elastic Compute Cloud)]] instances will get at least a private internal IPv4 and a public IPv6
- They can communicate using either IPv4 or IPv6 to the internet through an [[IGW (Internet Gateway)]]

## Troubleshoot
---
- If you cannot launch an EC2 instance in your subnet, it's because there's no available IPv4 in your subnet, because the IPv6 is very large
	- The solution is to create a new IPv4 [[CIDR]] in your subnet