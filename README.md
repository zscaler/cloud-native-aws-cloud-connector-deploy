
# **README for AWS CloudFormation**

This README serves as a quick start guide to deploy Zscaler Cloud Connector resources in an AWS cloud using AWS CloudFormation templates. To learn more about the resources created when deploying Cloud Connector with CloudFormation, see [Deployment Templates for Zscaler Cloud Connector](https://help.zscaler.com/cloud-connector/about-cloud-automation-scripts).

## **AWS Deployment Templates for CloudFormation**

Use this repository to create the deployment resources required to deploy and operate Cloud Connector in an existing virtual private cloud (VPC). To learn more about the steps for deploying Cloud Connector using a CloudFormation template, see [Deploying Cloud Connector with Amazon Web Services](https://help.zscaler.com/cloud-connector/deploying-cloud-connector-amazon-web-services).

## **1. Pre-Deployment Template**

Before deploying your Cloud Connectors using CloudFormation, you must upload the [**Pre-Deployment Template**](cloudformation-templates/zs_cc_cf_template_zscc_macro.yaml) to the AWS CloudFormation console to create a Pre-Deployment Template Stack.

## **2A. Create a stack in the CloudFormation console**

### **i. Starter Deployment Template**

Use the [**Starter Deployment Template**](cloudformation-templates/zs_cc_cf_template_simple.yaml) to create the resources needed to deploy and operate Cloud Connector in an existing VPC.

### **ii. Add-on Template with Gateway Load Balancer (GWLB) - ___Recommended___** 

Use the [**Add-on Template with GWLB**](cloudformation-templates/zs_cc_cf_template_gwlb.yaml) to distribute traffic across multiple Cloud Connectors and achieve high availability. Zscaler's recommended deployment method is Gateway Load Balancer (GWLB). <b>This add-on is only compatible with Starter Deployment Template as Auto Scaling deployments include GWLB automatically.</b>

### **iii. Add-on Template with ZPA - ___Optional___**

Use the [**Add-on Template with ZPA**](cloudformation-templates/zs_cc_cf_template_zpa_r53.yaml) to create the resources needed to enable the ZPA DNS resolver capability on Cloud Connector in an existing VPC.

## **2B. Create a stack in the CloudFormation console with Auto Scaling (Advanced Deployment)**

### **i. Starter Deployment Template with Auto Scaling and Gateway Load Balancer (GWLB)**
Use the [**Starter Deployment Template with Auto Scaling and Gateway Load Balancer (GWLB)**](cloudformation-templates/zs_cc_cf_template_asg_gwlb.yaml) to create the resources needed to deploy and operate Cloud Connector in an existing VPC and load balance traffic across multiple Cloud Connectors. Zscaler\'s recommended deployment method is Gateway Load Balancer (GWLB). GWLB distributes traffic across multiple Cloud Connectors and achieves high availability. For added resiliency and elasticity, Cloud Connectors are deployed via a Launch Template configured Auto Scaling group.

### **ii. Add-on Template with ZPA - ___Optional___**

Use the [**Add-on Template with ZPA**](cloudformation-templates/zs_cc_cf_template_zpa_r53.yaml) to create the resources needed to enable the ZPA DNS resolver capability on Cloud Connector in an existing VPC.
