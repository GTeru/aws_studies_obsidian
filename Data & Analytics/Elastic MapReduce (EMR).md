- EMR helps creating [Hadoop](https://hadoop.apache.org/) clusters (Big Data) to analyze and process vast amount of data
- Clusters can be made of hundreds of [[EC2 (Elastic Compute Cloud)]] instances
- EMR comes bundled with Apache Spark, HBase, Presto, Flink, etc...
- Takes care of provisioning and configuration
- Auto-scaling and integrated with [[EC2 Spot Instances]]
- Use cases
	- Data processing
	- Machine learning
	- Web indexing
	- Big data
	- etc...

## Node types
---
- Master node: manage cluster, coordinate, manage health - long running instance
- Core node: Run tasks and store data - long running
- Task node (optional): Just to run tasks - usually Spot Instance
- Purchasing options
	- On-demand: reliable, predictable, won't be terminated
	- Reserved (min 1 year): cost savings (EMR will automatically use if available)
	- Spot Instances: cheaper, can be terminated, less reliable
- Can have long-running clusters or transient (temporary) cluster