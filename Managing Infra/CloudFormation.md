---
tags:
  - Management
---
- Declarative way of outlining your AWS Infrastructure (IaC - Infras as Code), for any resources (most of them are supported)
- For example, within a CloudFormation template, you say:
	- I want a [[Security Group]]
	- I want two [[EC2 (Elastic Compute Cloud)]] instances using this security group
	- I want an [[S3]] bucket
	- I want a [[ELB (Elastic Load Balancer)]] in front of these machines
- Then CloudFormation creates those for you, in the __right order__, with the __exact configuration__ you specified

- Benefits 
	- IaC 
		- Excellent control
		- Changes to infrastructure are easily reviewed through code
	- Cost
		- Each resource within the stack is tagged with an identifier so you can easily see how much a stack costs you
		- You can estimate the costs of your resources using the CloudFormation template
		- Savings strategy: In Dev, you could automate deletion of templates ate 5PM and recreate them at 8AM, in a safer manner
	- Productivity
		- Ability to destroy and re-create infrastructure on the cloud on the fly
		- Automated generation of Diagram for your templates
		- Declarative programming (no need to figure out ordering and orchestration)
	- Community
		- Leverage existing templates on the web
		- Leverage documentation
	- Supports almost all AWS resources
		- You can use "custom resources" for resources that are not supported

## CloudFormation Stack Designer
---
- GUI tool to design AWS solutions, enabling visualizing, creation and editing of infrastructure stack.
	- See all resources and relations in the tool
