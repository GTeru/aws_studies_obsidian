FIFO (First In First Out) [[Simple Notification Service (SNS)]] queues 
- Limited throughput: 
	- 300 msg/s single messages
	- 3.000 msg/s batching
- Exactly-once send capabilities (by removing duplicates)
- Messages are processed in order by the consumer
- Queue name needs to end with __.fifo__
- Can have [[Simple Queue Service (SQS)]] Standard and [[FIFO Queues]] as subscribers