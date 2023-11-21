When a [[Simple Queue Service (SQS)]] consumer requests messages from the queue, it can optionally "wait" for messages to arrive if there are none in the queue, this process is called __Long Polling__

- Use cases
	- Reduce API calls when polling
	- Increasing efficiency and latency of your application
	- Login Polling is preferable to Short Polling
	- Wait time can be configured between 1 to 20 seconds
	- Can be enabled at the queue level or at the API level using __WaitTimeSeconds__
