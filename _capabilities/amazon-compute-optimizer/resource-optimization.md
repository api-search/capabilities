---
categories: []
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
- get rds recommendations
- check if the account is enrolled in amazon compute optimizer.
- get rightsizing recommendations for amazon ec2 instances to reduce costs.
- rds database recommendations.
- get ebs recommendations
- optimization findings summary.
- get optimization findings summary across all resource types.
- get rightsizing recommendations for amazon ebs volumes.
- get rightsizing recommendations for ecs services.
- cross-resource rightsizing recommendations for cost optimization.
- get rightsizing recommendations for amazon rds database instances and clusters.
- get rightsizing recommendations for ebs volumes.
- resource recommendations
- analyzes cost savings opportunities across compute resources.
- get rightsizing recommendations for lambda functions.
- Cloud Architect
- get lambda recommendations
- get a summary of optimization findings across all supported resource types in the account.
- get rightsizing recommendations for ec2 instances.
- FinOps Engineer
- get optimization summary
- lambda function recommendations.
- enrollment status management.
- get rightsizing recommendations for auto scaling groups.
- machine learning
- ecs service recommendations.
- reviews recommendations to rightsize infrastructure and improve performance.
- get enrollment status.
- get rightsizing recommendations for aws lambda functions.
- ebs volume recommendations.
- get enrollment status
- auto scaling group recommendations.
- get rightsizing recommendations for rds databases.
- finops
- get rightsizing recommendations for amazon ecs services.
- ec2
- aws
- get enrollment
- amazon
- get summary
- ec2 instance rightsizing recommendations.
- get ecs recommendations
- get asg recommendations
- cost optimization
- get ec2 recommendations
slug: resource-optimization
source_filename: resource-optimization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Compute Optimizer Resource Optimization\"\n  description: \"Workflow capability for AWS resource rightsizing and cost optimization recommendations across EC2 instances, Auto Scaling groups, EBS volumes, Lambda functions, ECS services, and RDS instances. Used by cloud architects and FinOps engineers to identify over-provisioned resources and reduce costs.\"\n  tags:\n    - Amazon\n    - AWS\n    - Cost Optimization\n    - Resource Recommendations\n    - FinOps\n    - EC2\n    - Machine Learning\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: compute-optimizer\n      location: ./shared/compute-optimizer.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: resource-optimization-api\n      description:\
  \ \"Unified REST API for Amazon Compute Optimizer resource rightsizing recommendations.\"\n      resources:\n        - path: /v1/recommendations/ec2\n          name: ec2-recommendations\n          description: \"EC2 instance rightsizing recommendations.\"\n          operations:\n            - method: GET\n              name: get-ec2-recommendations\n              description: \"Get rightsizing recommendations for EC2 instances.\"\n              call: \"compute-optimizer.get-ec2-instance-recommendations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations/auto-scaling\n          name: asg-recommendations\n          description: \"Auto Scaling group recommendations.\"\n          operations:\n            - method: GET\n              name: get-asg-recommendations\n              description: \"Get rightsizing recommendations for Auto Scaling groups.\"\n              call: \"compute-optimizer.get-auto-scaling-group-recommendations\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations/ebs\n          name: ebs-recommendations\n          description: \"EBS volume recommendations.\"\n          operations:\n            - method: GET\n              name: get-ebs-recommendations\n              description: \"Get rightsizing recommendations for EBS volumes.\"\n              call: \"compute-optimizer.get-ebs-volume-recommendations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations/lambda\n          name: lambda-recommendations\n          description: \"Lambda function recommendations.\"\n          operations:\n            - method: GET\n              name: get-lambda-recommendations\n              description: \"Get rightsizing recommendations for Lambda functions.\"\n              call: \"compute-optimizer.get-lambda-function-recommendations\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations/ecs\n          name: ecs-recommendations\n          description: \"ECS service recommendations.\"\n          operations:\n            - method: GET\n              name: get-ecs-recommendations\n              description: \"Get rightsizing recommendations for ECS services.\"\n              call: \"compute-optimizer.get-ecs-service-recommendations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations/rds\n          name: rds-recommendations\n          description: \"RDS database recommendations.\"\n          operations:\n            - method: GET\n              name: get-rds-recommendations\n              description: \"Get rightsizing recommendations for RDS databases.\"\n              call: \"compute-optimizer.get-rds-database-recommendations\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations/summary\n          name: recommendation-summary\n          description: \"Optimization findings summary.\"\n          operations:\n            - method: GET\n              name: get-summary\n              description: \"Get optimization findings summary across all resource types.\"\n              call: \"compute-optimizer.get-recommendation-summaries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/enrollment\n          name: enrollment\n          description: \"Enrollment status management.\"\n          operations:\n            - method: GET\n              name: get-enrollment\n              description: \"Get enrollment status.\"\n              call: \"compute-optimizer.get-enrollment-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type:\
  \ mcp\n      port: 9090\n      namespace: resource-optimization-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Compute Optimizer resource rightsizing and cost analysis.\"\n      tools:\n        - name: get-ec2-recommendations\n          description: \"Get rightsizing recommendations for Amazon EC2 instances to reduce costs.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"compute-optimizer.get-ec2-instance-recommendations\"\n          with:\n            account_ids: \"tools.account_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-asg-recommendations\n          description: \"Get rightsizing recommendations for Auto Scaling groups.\"\n          hints:\n            readOnly: true\n          call: \"compute-optimizer.get-auto-scaling-group-recommendations\"\n          with:\n            account_ids: \"tools.account_ids\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-ebs-recommendations\n          description: \"Get rightsizing recommendations for Amazon EBS volumes.\"\n          hints:\n            readOnly: true\n          call: \"compute-optimizer.get-ebs-volume-recommendations\"\n          with:\n            account_ids: \"tools.account_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-lambda-recommendations\n          description: \"Get rightsizing recommendations for AWS Lambda functions.\"\n          hints:\n            readOnly: true\n          call: \"compute-optimizer.get-lambda-function-recommendations\"\n          with:\n            account_ids: \"tools.account_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-ecs-recommendations\n          description: \"Get rightsizing recommendations for Amazon ECS services.\"\n         \
  \ hints:\n            readOnly: true\n          call: \"compute-optimizer.get-ecs-service-recommendations\"\n          with:\n            service_arns: \"tools.service_arns\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-rds-recommendations\n          description: \"Get rightsizing recommendations for Amazon RDS database instances and clusters.\"\n          hints:\n            readOnly: true\n          call: \"compute-optimizer.get-rds-database-recommendations\"\n          with:\n            account_ids: \"tools.account_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-optimization-summary\n          description: \"Get a summary of optimization findings across all supported resource types in the account.\"\n          hints:\n            readOnly: true\n          call: \"compute-optimizer.get-recommendation-summaries\"\n          with:\n            account_ids:\
  \ \"tools.account_ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-enrollment-status\n          description: \"Check if the account is enrolled in Amazon Compute Optimizer.\"\n          hints:\n            readOnly: true\n          call: \"compute-optimizer.get-enrollment-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-compute-optimizer/refs/heads/main/capabilities/resource-optimization.yaml
tags:
- Amazon
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
