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
