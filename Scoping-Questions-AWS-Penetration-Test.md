# AWS Pentest Scoping Questions

**What AWS-specific scoping questions should you ask as a practitioner, or prepare for as a business/product owner when undertaking an AWS penetration test?**

Here is what I use to better understand an AWS environment I’ll be penetration testing:

## General

1. **What is the primary goal of penetration testing?**
2. **What are the main areas of focus for this penetration test?**
3. **What is the general business purpose of the infrastructure, environment, or application?**
4. **Has penetration testing been performed previously?**

## Accounts

1. **What is the AWS Account ID in scope (12 digits), and provide any AWS Account Aliases (if applicable)?**
2. **Are AWS Organizations in use, and if so, provide the Management Account ID and all other Account IDs in scope.**
3. **For each AWS Account in scope, provide a brief description and any useful information about the account.**

## Services

1. **What AWS services are in use?**
2. **Are there any specific AWS services you are particularly concerned about?**
3. **For each service, describe its purpose, use, and connection within the environment.**
   - **Example:** DynamoDB is used for application user PII and data storage. Cognito is used for front-end user authentication. Lambda is used to handle user API requests and processing.
4. **Can you provide a high-level overview of your AWS architecture, including mention of any applicable VPCs, subnets, and key services used?**
5. **Please provide the latest architecture diagrams of your environment.**
   - In instances where no diagrams are provided, a built-in workload discovery tool, or a third-party tool like CloudMapper can be used:
     - [Workload Discovery on AWS](https://aws.amazon.com/solutions/implementations/workload-discovery-on-aws/)
     - [CloudMapper](https://github.com/duo-labs/cloudmapper)
     - [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/)

## Quantifying Size

1. **What is your approximate total monthly spend on AWS?**
2. **What are the approximate numbers of accounts, EC2 instances, databases, Lambda functions, user accounts, etc.?**

## Sensitive Data

1. **Where is sensitive data or Personally Identifiable Information (PII) stored within the environment?**
2. **What encryption methods are used for data at rest and in transit?**
3. **If your AWS environment were compromised, which service would you be most concerned about?**
4. **What are the key objectives, level of access or privileges, or end goal that should be targeted with testing?**
5. **What would be a worst-case scenario / what keeps you up at night in terms of an AWS environment breach?**
6. **What are the key assets or services you are most concerned about protecting?**

## Access

1. **Are any services publicly accessible?**
2. **Which services should we be able to see from an unauthenticated external perspective?**
3. **What services are publicly accessible but safeguarded behind authentication mechanisms?**
4. **What authentication methods are used for accessing AWS services, and what does a typical authentication flow look like?**
5. **Are there any third-party services used for authentication federation, such as Google, Microsoft, Okta, etc.?**

## Applications

1. **Is AWS supporting an application or service that should fall under the scope of this testing?**
2. **Please provide any API documentation, API flows, Swagger, etc., if applicable.**
3. **Walk me through the typical user flows (for each permission level) of the application and describe how the app is built on underlying AWS services.**

## Users

1. **Who is a typical user of the infrastructure, environment, or application?**
2. **Who typically accesses the AWS console?**
3. **How do development users typically access the infrastructure, environment, or application?**
4. **What are the typical roles provisioned within this environment, and what is the approximate breakdown of the number of users per role?**
5. **Are there any IAM users or roles with elevated privileges that we should be aware of?**

## Out of Scope

1. **List any assets or accounts within the AWS environment that are explicitly out of scope.**
2. **Are any of the services, data, or assets within the environment off-limits for testing?**
3. **Are there any specific testing techniques or tools that should not be used?**

## Additional Info

1. **What other information would be useful for me to know when testing your AWS environment?**
2. **Does your environment have any AWS native or third-party cloud monitoring/security solutions implemented?**
3. **Are there any other third-party integrations?**
4. **Is there any AWS monitoring or alerting teams/personnel that I should be aware of, or who should be notified before testing?**
5. **Are there any WAF (Web Application Firewall) or Shield configurations in place for DDoS protection?**
6. **What logging and monitoring solutions are implemented (e.g., CloudWatch, CloudTrail, GuardDuty)?**
7. **What security tools and services are implemented in your AWS environment to enhance security monitoring, incident response, and compliance, and how are they configured and used (e.g., Security Hub, AWS Config, Inspector, etc.)?**
