# AWS Pentest Scoping Questions
What AWS specific scoping questions should you ask as a practitioner, or prepare for as a business/product owner when taking on an AWS penetration test?

Here is what I use to better understand an AWS environment I’ll be pentesting.

## General
What is the primary goal for testing?
What are the main areas of focus?
Are there any compliance or regulatory requirements for testing?
What is the general business purpose for the infrastructure / environment / application?
Has penetration testing been performed previously?

## Logistics
What is the AWS Account ID in scope - ############ 12 digits, and provide any AWS Account Aliases (if applicable)
Are AWS Organizations in use, and if so, provide the Management Account ID, and all other Account IDs in scope.
For each AWS Account in scope, provide a brief description and any useful information about the account.

## Services
What AWS services are in use?
For each service, describe their purpose/use and connection within the environment.
	Example:
DynamoDB is used for application user PII and data storage.
Cognito is used for front-end user authentication.
Lambda is used to handle user API requests and processing.

## Sensitive Data
Where is sensitive data or Personally Identifiable Information stored in the environment?
If your AWS environment were compromised, which service would you be most concerned about?
What are the key objectives, level of access or privileges, or end goal that should be targeted with testing?
What would be a worst case scenario / keeps you up at night in terms of an AWS environment breach?

## Public Accessible
Are any services publicly accessible? 
Which services should we be able to see from an unauthenticated external perspective?
What services are publicly accessible but safeguarded behind authentication mechanisms?
What do you use for Authentication? Are there any third party services used for authentication federation, i.e. Google, Microsoft, Okta, etc.

## Aproximate Size
What is your approximate total monthly spend on AWS?
What are the approximate number of accounts, ec2 instances, databases, lambda functions, user accounts, etc.
Please provide the latest architecture diagrams of your environment
In instances where no diagrams are provided, a built in workload discovery tool, or a third party a tool like cloudmapper can be used 
https://aws.amazon.com/solutions/implementations/workload-discovery-on-aws/
https://github.com/duo-labs/cloudmapper
https://aws.amazon.com/architecture/icons/

## Applications
Is AWS supporting an Application or service that should fall under the scope of this testing?
Please provide any API docs, API flows, Swagger, etc if applicable.
Walk me through the typical user flows (for each permission level) of the application and describe how the app is built off of underlying AWS services.

## Users
Who is a typical user of the infrastructure / environment / application?
Who is a typical user accessing the AWS console?
How do dev users typically access the infrastructure / environment / application?
What are the typical roles provisioned within this environment, and what is the approximate breakdown of the number of users per role.

# Out of Scope
List any assets or accounts within the AWS environment that are explicitly out of scope
Are any of the services or data within the environment off limits for testing?

## Additional Info
What other information would be useful for me to know when testing your AWS environment?
Does your environment have any AWS native or 3rd party cloud monitoring/security solutions implemented? 
Are there any other third party integrations?
Is there any AWS monitoring or alerting teams/personnel that I should be aware of, or who should be notified before testing?

