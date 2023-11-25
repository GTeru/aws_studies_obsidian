FIFO (First In First Out) [[Simple Queue Service (SQS)]] queues 
- Limited throughput: 
	- 300 msg/s for single messages
	- 3.000 msg/s for batching
- Exactly-once send capabilities (by removing duplicates)
- Messages are processed in order by the consumer
- Queue name needs to end with __.fifo__
- __Group IDs__ are used if you need to group messages together and each one of them can have a consumer attached to their messages