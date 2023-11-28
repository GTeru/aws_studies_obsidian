Lifecycle Policy is a [[S3]] mechanism that lets you automate changing [[S3 Storage Classes]] depending on various parameters

__Note__ : There's some restrictions when changing S3 Storage Classes, you can refer to the image below or check this [link](https://docs.aws.amazon.com/AmazonS3/latest/userguide/lifecycle-transition-general-considerations.html)
![[change_aws_classes.png]]

## Policy Machanisms
---
- Transition Action - configure objects to transition to another storage class for example:
	- Move objects to Standard IA class 60 days after creation
	- Move to Glacier for archiving after 6 months
- Expiration Actions - configure objects to expire (delete) after some time
	- Access log files can be set to delete after a 365 days creation
	- Can be used to delete old versions of files (if versioning is enabled)
	- Can be used to delete incomplete Multi-Part uploads

- Rules can be created for
	- Certain __prefixes__ using _wildcards_ (e.g.: s3://cool_bucket/sounds/\*)
	- Certain __object Tags__ (e.g.: `Departament: Finance`)

## Storage Class Analysis
---
- Help decide when to transition objects to the right storage class
- Recommendations for __Standard__ and __Standard IA__
	- Does NOT work for One-Zone IA or Glacier
- Report is updated daily
- 24 to 48 hours to start seeing data analysis
- Good first step to create/improve Lifecycle Rules 