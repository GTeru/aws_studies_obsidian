---
tags:
  - Compute
---
- Fully managed batch processing at any scale
- Efficiently run 100.000s of computing batch jobs on AWS
- A "batch" job is a job with a start and an end (opposed to a server)
- Batch will dynamically launch [[EC2 (Elastic Compute Cloud)]] instances or [[EC2 Spot Instances]]
- AWS Batch provisions the right amount of compute/memory
- You submit or schedule batch jobs and AWS batch does the rest
- Batch jobs are defined as __Docker images__ and run on [[ECS (Elastic Container Service)]]
- Helpful for cost optimizations and focusing less on the infrastructure

## Batch vs Lambda
---
- Lambda
	- Time limit
	- Limited runtimes
	- Limited temporary disk space
	- Serverless
- Batch
	- No time limit
	- Any runtime as long as it's packaged as a Docker image
	- Rely on [[EBS (Elastic Block Storage)]] / instance store for disk space
	- Relies on EC2 (can be managed by AWS)