![fan_out_pattern.png](./Images/fan_out_pattern.png)
- Push once in [[SNS (Simple Notification Service)]], receive in all [[SQS (Simple Queue Service)]] queues that are subscribers
- Fully decoupled, no data loss
- SQS allows
	- Data persistence
	- Delayed processing
	- Retries of work
- Ability to add more SQS subscribers over time
- Make sure your SQS __access policy__ allows for SNS to write
- Cross [[AWS Region]] delivery: works with SQS queues in other regions
  