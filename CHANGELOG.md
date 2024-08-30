## 1.3.3 - 2024-08-30

------------
ENHANCEMENTS:
* add support for AWS China Marketpkace deployments in the AWS China (Beijing) region and AWS China (Ningxia) region
* refactor: add china marketplace specific product-code ("axnpwhsb4facossmbm1h9yad6") AMI lookup in macro template 

BUG FIXES:
* fix: asg lambda runtime selection for unsupported regions
* fix: macro lambda runtime selection for unsupported regions

## 1.3.2 - 2024-08-26

------------
ENHANCEMENTS:
* refactor: add sns:ListSubscriptions and sns:Unsubscribe permissions to cc_tags_policy_document for increased performance supporting multi-account workload tags
* refactor: CC VM EC2 instance type constraint cleanup (removal of t3a.medium and c4.4xlarge)

## 1.3.1 - 2024-05-13

------------
ENHANCEMENTS:
* feat: add c6in family as supported EC2 instance type

## 1.3.0 - 2024-04-26

------------
FEATURES:
* feat: change HeathCheckGracePeriod default to 900 seconds to prevent instance termination in Auto Scaling Group when moved to InService
* feat: change Python runtime for Lambda to use 3.12 version 
* feat: default arm64 architecture. This is more for cost/peformance benefit.
* feat: add parameter AsgZonalEnabled for customization when more than one Subnet/AZ selected to deploy either one ASG per AZ or one ASG spanning all AZs

BUG FIXES:
* fix: logic when multiple ASGs are created to only assign one unique Subnet/AZ in each ASG
* fix: set CcAsgCloudwatchSchedulerEventRule scheduler to 1 minute

ENHANCEMENTS:
* add: Ingress/Egress Security Group rule granularity for least privilege connectivity
* add: parameter ZscalerSupportServerRuleEnabled for Zscaler Support Tunnel connectivity with SG creation
* add: pre-deployment macro updates for Zscaler support tunnel endpoint IP lookup by Cloud
* docs: general UX improvements

## 1.2.1 - 2024-02-22

BUG FIXES:
* fix: aws lambda python runtime version update

## 1.2.0 - 2023-12-16

------------
FEATURES:
* feat: add optional IAM Policy for AWS Workload Tags support with Cloud Connector Instance IAM Role creation. Permissions include:
    - sqs:DeleteMessage
    - sqs:ReceiveMessage
    - sqs:GetQueueUrl
    - sqs:GetQueueAttributes
    - sqs:SetQueueAttributes
    - sqs:DeleteQueue
    - sqs:CreateQueue
    - sns:Subscribe

BUG FIXES:
* fix: add log group configuration to asg lambda
* fix: default http probe port value

## [1.1.0] - 2023-11-1

------------
FEATURES:
* AWS GovCloud (US) support

BUG FIXES:
* fix: arn support for all aws partitions


## [1.0.1] - 2023-10-23

------------
BUG FIXES:
* fix: change ZscalerOsAmi type to String with Constraint

## [1.0.0] - 2023-10-19

------------
BREAKING CHANGES:
* Zscaler Cloud Connector AMI version > ZS6.1.25.0 support for default interface swap of both autoscaling and non-autoscaling deployments. Service interface is now ENA0 and Management interface is now ENA1.

FEATURES:
* Auto Scaling Group official release
* Medium and Large Cloud Connector instance official release
* EC2 instance type changes:
    - new default/recommend EC2 type for small CCs: m6i.large; medium/large: m6i.4xlarge
    - add: m5n, m6i, and c6i family support
    - remove: m5 family support

BUG FIXES:
* fix: asg - move cc instance size to ec2 instance type validation from macro to cft
* fix: GWLB rebalance, flowstickiness and health attribs (#24)

## [0.1.3] - 2023-06-20

------------
- fix: enforce imdsv2 for cloudconnector instances



## [0.1.2] - 2023-03-16

------------
- ci: ci: Add detect-secrets to pre-commit
- fix: userdata formatting for simple template
- fix: pr comments for secrets lint
- fix: CcIamRole to limit SSM access, callhome
- fix: Limit SSM-IAM-Access



## [0.1.1] - 2022-12-13

------------
- ci: fix type of changes for commit message
- ci: git action for cfn-lint
- docs: more comprehensive readme doc



## [0.1.0] - 2022-08-27

------------
- Chore: cfn-lint changes. [Anirudh Chari]
- Chore: .gitignore initial commit. [Anirudh Chari]
- Refactor(cloudformation yaml): Move to new home. [Anirudh Chari]
- Feat: add-on template with gwlb initial commit. [Anirudh Chari]
- Feat: add-on template with zpa initial commit. [Anirudh Chari]
- Feat: starter deployment template initial commit. [Anirudh Chari]
- Feat: pre-deployment template initial commit. [Anirudh Chari]
- Chore: lint and hook config files. [Anirudh Chari]
- Docs: Initial README and CHANGELOG. [Anirudh Chari]
