---
tags:
  - Storage
---
- Based on PostgreSQL, but it's not used for OLTP
- It's OLAP - online analytical processing (analytics and data warehousing)
- 10x better performance than other data warehouses, scale to PB of data
- __Columnar__ storage of data (instead of row based) & parallel query engine
- Pay as you go based on the instances provisioned
- Has SQL interface for performing the queries
- BI tools such as [[Amazon QuickSight]] or Tableau integrate with it
- Faster queries/joins/aggregations than [[Athena]] because of indexing

## Redshift Nodes
---
- Leader node: for query planning, results aggregation
- Compute node: performing queries, send results to leader
- Node size is provisioned in advance
- Can use Reserved Instance for cost savings

## Snapshots & DR
---
- RedShift has multi-[[Availability Zone (AZs)]] mode for some clusters
- Snapshots are point in time backups of a cluster, stored internally in S3
	- Incremental (only what has changed is saved)
- Restore snapshot in a new cluster
- Automated: every 8 hours, every 5Gb, or on a schedule, able to set retention period
- Manual: snapshots are retained until you delete it
- Able to configure RedShift to automatically copy snapshots (automated or manual) of a cluster to another [[AWS Region]]

## Examples of Loading data
---
![redshift_load_data_examples.png](redshift_load_data_examples.png)

## RedShift Spectrum
---
- Query data that is already in [[S3]] without loading it
- Must have a RedShift cluster available to start the query
- Query is submitted to thousands of RedShift Spectrum nodes