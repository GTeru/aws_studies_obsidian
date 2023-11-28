CloudFront is the CDN (Content Delivery Network) solution of AWS

- Improves read performance, since content is cached at edge locations
- Improves users experience
- 216 points of presence globally (edge locations)
- DDoS protection (because it's a worldwide service), integration with Shield and AWS [[Web Application Firewall (WAF)]]
P
## Origins
---
- [[S3]] buckets
	- For distributing files and caching them at the edge locations
	- Enhance security with CloudFront Origin Access Control (OAC)
		- OAC is replacing Origin Access Identity (OAI)
	- CloudFront can be used as an ingress (to upload files to S3)
- Custom Origin (HTTP)
	- [[Application Load Balancer (ALB)]]
	- [[EC2 (Elastic Compute Cloud)]]
	- S3 Website (must first enable the bucket as a static S3 [[Static Website Hosting]])
	- Any HTTP backend you want

## CloudFront vs S3 Cross Region Replication
---
- Cloudfront
	- Global Edge network (no setup needed)
	- Files are cached for a TTL (which is configurable)
	- Great for static content that must be available anywhere
- S3 Cross Region [[Replication]]
	- Must be setup for each region you want replication to happen
	- Files are updated in near real-time
	- Read only
	- Great for dynamic content that needs to be available at low-latency in few regions