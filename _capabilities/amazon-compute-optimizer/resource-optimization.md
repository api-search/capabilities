---
consumed_apis:
- compute-optimizer
description: Workflow capability for AWS resource rightsizing and cost optimization recommendations across EC2 instances, Auto Scaling groups, EBS volumes, Lambda functions, ECS services, and RDS instances. Used by cloud architects and FinOps engineers to identify over-provisioned resources and reduce costs.
layout: capability
name: Amazon Compute Optimizer Resource Optimization
operations:
- description: Get rightsizing recommendations for EC2 instances.
  method: GET
  name: get-ec2-recommendations
  path: /v1/recommendations/ec2
- description: Get rightsizing recommendations for Auto Scaling groups.
  method: GET
  name: get-asg-recommendations
  path: /v1/recommendations/auto-scaling
- description: Get rightsizing recommendations for EBS volumes.
  method: GET
  name: get-ebs-recommendations
  path: /v1/recommendations/ebs
- description: Get rightsizing recommendations for Lambda functions.
  method: GET
  name: get-lambda-recommendations
  path: /v1/recommendations/lambda
- description: Get rightsizing recommendations for ECS services.
  method: GET
  name: get-ecs-recommendations
  path: /v1/recommendations/ecs
- description: Get rightsizing recommendations for RDS databases.
  method: GET
  name: get-rds-recommendations
  path: /v1/recommendations/rds
- description: Get optimization findings summary across all resource types.
  method: GET
  name: get-summary
  path: /v1/recommendations/summary
- description: Get enrollment status.
  method: GET
  name: get-enrollment
  path: /v1/enrollment
personas: []
provider_name: Amazon Compute Optimizer
provider_slug: amazon-compute-optimizer
search_terms:
- ecs service recommendations.
- ec2
- check if the account is enrolled in amazon compute optimizer.
- cross-resource rightsizing recommendations for cost optimization.
- get optimization summary
- get rightsizing recommendations for rds databases.
- get ecs recommendations
- get rightsizing recommendations for amazon ec2 instances to reduce costs.
- ec2 instance rightsizing recommendations.
- get rightsizing recommendations for amazon ebs volumes.
- get enrollment status.
- Cloud Architect
- aws
- get rightsizing recommendations for amazon rds database instances and clusters.
- get enrollment
- machine learning
- finops
- ebs volume recommendations.
- get rightsizing recommendations for ebs volumes.
- get rds recommendations
- get rightsizing recommendations for aws lambda functions.
- reviews recommendations to rightsize infrastructure and improve performance.
- analyzes cost savings opportunities across compute resources.
- lambda function recommendations.
- get asg recommendations
- amazon
- auto scaling group recommendations.
- get rightsizing recommendations for lambda functions.
- get ebs recommendations
- get rightsizing recommendations for amazon ecs services.
- optimization findings summary.
- get optimization findings summary across all resource types.
- get rightsizing recommendations for ecs services.
- get summary
- get lambda recommendations
- get ec2 recommendations
- resource recommendations
- FinOps Engineer
- cost optimization
- get a summary of optimization findings across all supported resource types in the account.
- get enrollment status
- rds database recommendations.
- enrollment status management.
- get rightsizing recommendations for auto scaling groups.
- get rightsizing recommendations for ec2 instances.
slug: resource-optimization
tags:
- Amazon
- AWS
- Cost Optimization
- Resource Recommendations
- FinOps
- EC2
- Machine Learning
tools:
- description: Get rightsizing recommendations for Amazon EC2 instances to reduce costs.
  hints:
    openWorld: false
    readOnly: true
  name: get-ec2-recommendations
- description: Get rightsizing recommendations for Auto Scaling groups.
  hints:
    readOnly: true
  name: get-asg-recommendations
- description: Get rightsizing recommendations for Amazon EBS volumes.
  hints:
    readOnly: true
  name: get-ebs-recommendations
- description: Get rightsizing recommendations for AWS Lambda functions.
  hints:
    readOnly: true
  name: get-lambda-recommendations
- description: Get rightsizing recommendations for Amazon ECS services.
  hints:
    readOnly: true
  name: get-ecs-recommendations
- description: Get rightsizing recommendations for Amazon RDS database instances and clusters.
  hints:
    readOnly: true
  name: get-rds-recommendations
- description: Get a summary of optimization findings across all supported resource types in the account.
  hints:
    readOnly: true
  name: get-optimization-summary
- description: Check if the account is enrolled in Amazon Compute Optimizer.
  hints:
    readOnly: true
  name: get-enrollment-status
---
