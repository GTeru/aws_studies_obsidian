- [[CloudWatch]] service to collect, aggregate, summarize metrics and logs from containers
- Available for containers on 
	- [[ECS (Elastic Container Service)]]
	- [[EKS (Elastic Kubernetes Service)]]
	- Kubernetes platforms on [[EC2 (Elastic Compute Cloud)]]
	- [[AWS Fargate]] (both for ECS and EKS)
- In Amazon EKS and Kubernetes, Container Insights is using a containerized version of [[CloudWatch Agent]] to discover containers

## Lambda Insights
---
- Monitoring and troubleshooting solution for serverless applications running on [[AWS Lambda]]
- Collects, aggregates and summarizes system-level metrics including CPU time, memory, disk and network
- Collects, aggregates and summarizes diagnostic information such as cold starts and Lambda worker shutdowns
- Lambda Insights is provided as a Lambda layer

## Contributor Insights
---
- Analyzes log data and create time series that display contributor data
	- See metrics about the top-N contributors
	- The total number of unique contributors and their usage
- Helps find top talkers and understand who or what is impacting system performance
- Works for any AWS-generated logs ([[VPC]], DNS, etc...)
	- For example, find bad hosts, __identify the heaviest network users__ or find the URLs that generate the most errors.
- You can either build rules from scratch or use sample rules AWS creates (which leverages your [[CloudWatch Logs]])
- Also provides built-in rules that can be used to analyze metrics from other AWS services

## Application Insights
---
- Provides automated dashboards that show potential problems with monitored applications to help isolate ongoing issues
- Powered by [[SageMaker]]
- Enhanced visibility into your application health to reduce the time it takes to troubleshoot and repair your application
- Findings and alerts are sent to [[AWS EventBridge]] and SSM OpsCenter