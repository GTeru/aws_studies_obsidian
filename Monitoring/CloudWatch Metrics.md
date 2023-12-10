- [[CloudWatch]] provides metrics for every service in AWS
- __Metric__ is a variable to monitor (CPUUtilization, MemoryUsage, etc...)
- Metrics belong to __namespaces__
- __Dimension__ is an attribute of a metric (instance id, environment, etc...)
- Up to 30 dimensions per metric
- Metrics have __timestamps__
- Can create CloudWatch dashboards of metrics
- Can create CloudWatch Custom Metrics (for the RAM for example)

## Metric Streams
---
- Stream metrics to a destination of your choice
	- [[Kinesis Data Firehose]] (and then it's destinations)
	- 3rd party service provider: Datadog, New Relic, etc...
- Option to filter metrics to stream a subset of metrics