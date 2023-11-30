- Fully managed, highly available with replicatio across multiple [[Availability Zone (AZs)]]
- NoSQL database - with transaction support
- Scales to massive workloads, distributed database
- Millions of requests per second, trillions of row, 100s of Tb of storage
- Fast and consistent in performance (single-digit milisecond)
- Integrated with [[IAM]] for security, authoratization and administration
- Low cost and auto-scaling capabilities
- No maintenance or patching, always available
- Standard & Infrequent Access (IA) Table Class

## Basic
---
- DynamoDB is made of __Tables__
	- Each one has a __Primary Key__ (must be decided at creation time)
	- Each table can have infinite number of __items__ (= rows)
	- Each item has __attributes__ (can be added over time and can be null)
	- Maximum size of item is 400Kb
	- Data types supported are
		- Scalar Types: String, Number, Binary, Boolean, Null
		- Document Types: List, Map
		- SetTypes: String Set, Number Set, Binary Set
- Therefore, in DynamoDB you can rapidly evolve schemas

## Read/Write Capacity Modes
---
- Control how to manage table's capacity (read/write throughput)
- Provisioned Mode (default)
	- Specify the number of reads/writes per second
	- Need to plan capacity beforehand
	- Pay for __provisioned__ Read Capacity Units (RCU) & Write Capacity Units (WCU)
	- Possibility to add __auto-scaling__ mode for RCU & WCU
- On-Demand Mode
	- Read/Writes automatically scales up/down with workload
	- No capacity planning needed
	- Pay for use -> way more expensive
	- Good for unpredictable workloads or sudden spikes