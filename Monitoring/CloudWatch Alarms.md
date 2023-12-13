- [[CloudWatch]] Alarms are used to trigger notifications for any metric
- Various options (sampling, % max, min, etc...)
- Alarm state
	- OK
	- INSUFFICIENT_DATA
	- ALARM
- Period
	- Length of time in seconds to evaluate the metric
	- High resolution custom metrics: 10sec, 30sec or multiple 60sec

## Targets
---
- Stop, terminate, reboot, recover an [[EC2 (Elastic Compute Cloud)]] instance
- Trigger [[EC2 Auto Scaling Groups (ASG)]]
- Send notification to [[SNS (Simple Notification Service)]]

## Composite Alarms
---
- Alarms are related to a single metric
- Composite alarms are monitoring the states of multiple other alarms
- AND or OR operators
- Helpful to reduce "alarm noise" by creating a complex composite alarm

## EC2 Instance Recovery
---
- Status Check
	- Instance status -> check the EX2 VM
	- System status -> check underlying hardware
- Recovery: Same private, public, elastic IP, metadata, placement group

- Alarms can be created based on CloudWatch Logs Metrics Filters
- To test alarms and notifications, set the alarm state to Alarm using CLI
