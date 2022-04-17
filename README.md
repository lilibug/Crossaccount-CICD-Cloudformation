# Crossaccount-CICD-Cloudformation
Cross-account deployment using CI/CD pipeline to deploy Lambda API

<br> <b> GOAL OF THE INFRASTRUCTURE </b>

<br> The goal of the infrastructure is to achieve an automated deployment of the application across different AWS accounts.

<br> <b> ARCHITECTURE FRAMEWORK </b>

<B> Operational Excellence Pillar: </B>
The operational excellence pillar focuses on running and monitoring systems, and continually improving processes and procedures which includes automating changes, responding to events, and defining standards to manage daily operations

<b> Security Pillar </b>
The security pillar focuses on protecting information and systems which includes confidentiality and integrity of data, managing user permissions, and establishing controls to detect security events.

<b> Reliability Pillar </b>
The reliability pillar focuses on workloads performing their intended functions and how to recover quickly from failure to meet demands which includes distributed system design, recovery planning, and adapting to changing requirements.

<b> Cost Optimization Pillar </b>
The cost optimization pillar focuses on avoiding unnecessary costs which includes understanding spending over time and controlling fund allocation, selecting resources of the right type and quantity, and scaling to meet business needs without overspending.

<b> Performance Efficiency Pillar </b>
The performance efficiency pillar focuses on structured and streamlined allocation of computing resources. which includes selecting resource types and sizes optimized for workload requirements, monitoring performance, and maintaining efficiency as business needs evolve

<b> THE DESIGN SOLUTION OVERVIEW </b>

Prerequisites
Two AWS accounts were identified and designated:

Tools – The AWS account where pipeline resides </br>
Target – The AWS account where deployment occurs

![image](https://user-images.githubusercontent.com/88491497/163722581-b62742e7-e508-43ef-b250-0090f9b0be78.png)

This target account consists of an IAM role that trusts the tools account and provides the required deployment-specific permissions. This IAM role is assumed by AWS CodeBuild in the tools account to carry out deployment. 

AWS CloudFormation execution role was created to be assumed by AWS CloudFormation in the target account. This role has permissions to create your API resources, such as a Lambda function and Amazon API Gateway, in the target account.

In the tools account, the CI/CD pipeline is built using AWS CloudFormation, AWS CodePipeline, AWS CodeBuild, and AWS CodeCommit. 

<b> Result </b>
  
A fully functioning CI/CD pipeline that deploys your API in the target account. The pipeline starts automatically every time you check in your changes into your CodeCommit repository.

