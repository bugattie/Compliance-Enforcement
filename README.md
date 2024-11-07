## AWS Cloud Quest: Security - Compliance Enforcement with IaC

This repository provides a CloudFormation template (deployment.yaml) to automate security compliance enforcement for your AWS Resources, along with a corresponding architecture diagram.

#### Enforcing Security with Automation

This solution leverages AWS Config, Systems Manager, and Lambda to continuously monitor EC2 instances, identify non-compliance issues, and trigger automated remediation actions.

#### Key Features:

- **Continuous Monitoring**: AWS Config monitors EC2 instances against predefined rules, ensuring they meet your compliance requirements.
- **Automated Remediation**: Upon detecting non-compliance, Lambda functions are invoked to execute Systems Manager Automation documents for corrective actions.
- **Configuration Tracking**: AWS Config tracks configuration changes, enabling you to audit compliance history.
- **Infrastructure as Code (IaC)**: The CloudFormation template facilitates consistent and repeatable deployment of the compliance enforcement solution.

#### Understanding the Architecture

The architecture diagram depicts the interactions between the involved AWS services:

- **AWS Config:** Continuously monitors EC2 instances and detects configuration changes.
- **AWS Systems Manager:** Provides tools for managing and automating actions on EC2 instances. It executes Automation documents triggered by CloudWatch Events.
- **AWS Lambda:** Serverless functions invoked by configuration changes detected by AWS Config. They initiate remediation actions using Systems Manager documents.
- **Amazon EC2:** The target resources being monitored for compliance.
- **Amazon S3 (Optional):** Can be used to store configuration rules or Automation documents for version control and reusability.
- **ConfigRole:** Grants AWS Config permission to assume the role and access S3 to store configuration data.
- **LambdaExecutionRole:** Grants the Lambda function permissions to interact with AWS services like EC2, Config, and Systems Manager for remediation actions.

#### Deployment Instructions

- **Review and Customize:** Carefully examine the deployment.yaml file and adjust configuration rules and remediation actions to align with your specific compliance requirements.
- **Deploy the CloudFormation Template:** Use the AWS CLI or CloudFormation console to deploy the template.

#### Important Note:

This template serves as a foundational example for compliance enforcement. You may need to adapt it to your specific security and compliance needs.
