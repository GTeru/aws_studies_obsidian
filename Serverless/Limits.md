[[AWS Lambda]] limits

## Per [[AWS Region]]
---
- Execution
	- Memory allocation 128Mb - 10Gb (1 Mb increments)
	- Maximum execution time: 900 seconds (15 minutes)
	- Environment variables (4Kb)
	- Disk capacity in the _"function container"_ (in /tmp): 512 Mb to 10 Gb
	- Concurrency executions: 1000 (can be increased via request)
- Deployment
	- Deployment size (compressed .zip): 50Mb
	- Uncompressed deployment (code + dependencies): 250Mb
	- Can use the _/tmp_ directory to load other files at startup
	- Size of environment variables: 4Kb