# AWS-SAA Cheat Sheet

Welcome to the **AWS Certified Solutions Architect - Associate (AWS-SAA)** Cheat Sheet repository! \
This cheat sheet is designed to help you quickly review key concepts, services, and best practices necessary for the AWS-SAA certification.

## Table of Contents

1. [Overview](#overview)
2. [How to Use](#how-to-use)
3. [Detailed Explaination](#detailed-explaination)
4. [Services Cheatsheet](#services-cheatsheet)
5. [Contributing](#contributing)
6. [License](#license)

---

## Overview

The AWS-SAA certification validates your ability to design and implement distributed systems on AWS. This cheat sheet provides concise, exam-focused information to:

- Review core AWS services.
- Understand design principles for cloud architecture.
- Learn key terms and concepts for the AWS-SAA exam.

## How to Use

1. **Download or Clone the Repository:**
   ```bash
   git clone https://github.com/manuka99/aws-saa-cheatsheet.git
   ```
2. **Browse the Sections:** The content is organized into topics to cover the AWS-SAA exam domains.
3. **Revise Key Concepts:** Use the cheat sheet for quick revisions during your preparation.

This cheat sheet is best used alongside hands-on practice in the AWS Management Console and other learning resources.

## Detailed Explaination

The cheat sheet covers the following sections:

1. [Introduction](docs/01_intro.md)
2. [Getting Started](docs/02_get_started.md)
3. [IAM (Identity and Access Management)](docs/03_iam.md)
4. [EC2 Basics](docs/04_ec2_basics.md)
5. [EC2 Associate](docs/05_ec2_associate.md)
6. [EBS, Instance Storage, and EFS](docs/06_ebs_inst_storage_efs.md)
7. [ELB and Auto Scaling Groups](docs/07_elb_asg.md)
8. [RDS, Aurora, and Caching](docs/08_rds_aurora_cache.md)
9. [Route 53](docs/09_route_53.md)
10. [Classic Architecture](docs/10_classic_architecture.md)
11. [S3](docs/11_s3.md)
12. [Advanced S3](docs/12_s3_advance.md)
13. [S3 Security](docs/13_s3_security.md)
14. [CloudFront and Global Accelerator](docs/14_cludfrnt_gbl_acelrator.md)
15. [Storage Extras](docs/15_storage_extras.md)
16. [SQS, SNS, Kinesis, and MQ](docs/16_sqs_sns_kinesis_mq.md)
17. [ECS, Fargate, ECR, and EKS](docs/17_ecs_fargate_ecr_eks.md)
18. [Serverless](docs/18_serverless.md)
19. [Serverless Architecture](docs/19_serverless_arch.md)
20. [Databases](docs/20_databases.md)
21. [Data Analytics](docs/21_data_analytics.md)
22. [Machine Learning](docs/22_machine_learning.md)
23. [CloudWatch, CloudTrail, and Config](docs/23_cludwatch_cludtrail_config.md)
24. [Advanced Identity](docs/24_advance_identity.md)
25. [KMS, SSM Parameter Store, Shield, and WAF](docs/25_kms_ssm_sheild_waf.md)
26. [VPC](docs/26_vpc.md)
27. [Disaster Recovery and Migrations](docs/27_dis_recv_migrations.md)
28. [Solution Architectures](docs/28_solution_archs.md)
29. [Other Services](docs/29_other_services.md)

## Services Cheatsheet

| **Category**                           | **Services**                                                                                                                                                                                                                                                                                                                                                                                      |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Analytics**                          | Amazon Athena, AWS Data Exchange, AWS Data Pipeline, Amazon EMR, AWS Glue, Amazon Kinesis, AWS Lake Formation, Amazon MSK, Amazon OpenSearch Service, Amazon QuickSight, Amazon Redshift                                                                                                                                                                                                          |
| **Application Integration**            | Amazon AppFlow, AWS AppSync, Amazon EventBridge, Amazon MQ, Amazon SNS, Amazon SQS, AWS Step Functions                                                                                                                                                                                                                                                                                            |
| **AWS Cost Management**                | AWS Budgets, AWS Cost and Usage Report, AWS Cost Explorer, Savings Plans                                                                                                                                                                                                                                                                                                                          |
| **Compute**                            | AWS Batch, Amazon EC2, Amazon EC2 Auto Scaling, AWS Elastic Beanstalk, AWS Outposts, AWS Serverless Application Repository, VMware Cloud on AWS, AWS Wavelength                                                                                                                                                                                                                                   |
| **Containers**                         | Amazon ECS Anywhere, Amazon EKS Anywhere, Amazon EKS Distro, Amazon ECR, Amazon ECS, Amazon EKS                                                                                                                                                                                                                                                                                                   |
| **Database**                           | Amazon Aurora, Amazon Aurora Serverless, Amazon DocumentDB, Amazon DynamoDB, Amazon ElastiCache, Amazon Keyspaces, Amazon Neptune, Amazon QLDB, Amazon RDS, Amazon Redshift                                                                                                                                                                                                                       |
| **Developer Tools**                    | AWS X-Ray                                                                                                                                                                                                                                                                                                                                                                                         |
| **Front-End Web and Mobile**           | AWS Amplify, Amazon API Gateway, AWS Device Farm, Amazon Pinpoint                                                                                                                                                                                                                                                                                                                                 |
| **Machine Learning**                   | Amazon Comprehend, Amazon Forecast, Amazon Fraud Detector, Amazon Kendra, Amazon Lex, Amazon Polly, Amazon Rekognition, Amazon SageMaker, Amazon Textract, Amazon Transcribe, Amazon Translate                                                                                                                                                                                                    |
| **Management and Governance**          | AWS Auto Scaling, AWS CloudFormation, AWS CloudTrail, Amazon CloudWatch, AWS CLI, AWS Compute Optimizer, AWS Config, AWS Control Tower, AWS Health Dashboard, AWS License Manager, Amazon Managed Grafana, Amazon Managed Service for Prometheus, AWS Management Console, AWS Organizations, AWS Proton, AWS Service Catalog, AWS Systems Manager, AWS Trusted Advisor, AWS Well-Architected Tool |
| **Media Services**                     | Amazon Elastic Transcoder, Amazon Kinesis Video Streams                                                                                                                                                                                                                                                                                                                                           |
| **Migration and Transfer**             | AWS Application Discovery Service, AWS Application Migration Service, AWS DMS, AWS DataSync, AWS Migration Hub, AWS Snow Family, AWS Transfer Family                                                                                                                                                                                                                                              |
| **Networking and Content Delivery**    | AWS Client VPN, Amazon CloudFront, AWS Direct Connect, ELB, AWS Global Accelerator, AWS PrivateLink, Amazon Route 53, AWS Site-to-Site VPN, AWS Transit Gateway, Amazon VPC                                                                                                                                                                                                                       |
| **Security, Identity, and Compliance** | AWS Artifact, AWS Audit Manager, AWS Certificate Manager, AWS CloudHSM, Amazon Cognito, Amazon Detective, AWS Directory Service, AWS Firewall Manager, Amazon GuardDuty, AWS IAM Identity Center, AWS IAM, Amazon Inspector, AWS KMS, Amazon Macie, AWS Network Firewall, AWS RAM, AWS Secrets Manager, AWS Security Hub, AWS Shield, AWS WAF                                                     |
| **Serverless**                         | AWS AppSync, AWS Fargate, AWS Lambda                                                                                                                                                                                                                                                                                                                                                              |
| **Storage**                            | AWS Backup, Amazon EBS, Amazon EFS, Amazon FSx, Amazon S3, Amazon S3 Glacier, AWS Storage Gateway                                                                                                                                                                                                                                                                                                 |

## Contributing

We welcome contributions from the community to keep this cheat sheet up-to-date! If you have suggestions, corrections, or additional content to add, please:

1. Fork the repository.
2. Create a feature branch.
3. Submit a pull request with your changes.

## License

This cheat sheet is released under the [MIT License](LICENSE). Feel free to use, modify, and share it as needed.

---

Happy Learning and Best of Luck with Your AWS-SAA Certification! 🎉
