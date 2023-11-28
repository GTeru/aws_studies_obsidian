[[CloudFront]] can be configured to have [[EC2 (Elastic Compute Cloud)]] or  [[Application Load Balancer (ALB)]] as Origins

## EC2 Setup
---
- EC2 (Elastic Compute Cloud) instances needs to be public because the edge locations nedds to be able to make requests into the instances

- [Edge Locations IPs](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/LocationsOfEdgeServers.html) needs to be allowed into the instance [[Security Groups]]

## ALB
---
- ALB needs to be public and allow Edge Locations IPs traffic into it.