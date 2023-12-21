It's basically the AWS offering of dockerhub, where you can store and manage Docker images.
- Amazon ECR has two kinds of repositories
	1. Private repository
	2. Public repository ([Amazon ECR Public Gallery](https://gallery.ecr.aws/))
- Fully integrated with [[ECS (Elastic Container Service)]], backed by [[S3 (Simple Storage Service)]]
- Access is controlled through [[IAM]] roles (meaning any permission erros are probably a IAM policy error)  
- Supports image vulnerability scanning, versioning, image tags, image lifecycle, etc...
