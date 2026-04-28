---
aliases: []
common_operations:
- invoke-function
- list-functions
- deploy-function
- get-function-logs
description: 'Function-as-a-Service compute — short-lived event-triggered functions,

  HTTP triggers, queue triggers, scheduled triggers. Includes AWS Lambda,

  Azure Functions, GCP Cloud Functions, Cloudflare Workers.

  '
domain: infrastructure
implementation_count: 5
implementations:
- capability_name: Amazon Lambda Workflow
  capability_slug: amazon-lambda-workflow
  capability_url: https://capabilities.apis.io/capabilities/amazon-lambda/amazon-lambda-workflow/
  consumed_api_count: 1
  operation_count: 0
  provider_name: Amazon Lambda
  provider_slug: amazon-lambda
  tags:
  - Amazon Lambda
  - AWS
  - Workflow
  tool_count: 6
- capability_name: Amazon SAR Serverless App Management
  capability_slug: serverless-app-management
  capability_url: https://capabilities.apis.io/capabilities/amazon-serverless-application-repository/serverless-app-management/
  consumed_api_count: 1
  operation_count: 6
  provider_name: Amazon Serverless Application Repository
  provider_slug: amazon-serverless-application-repository
  tags:
  - Amazon Serverless Application Repository
  - Serverless
  - Lambda
  - SAM
  - DevOps
  tool_count: 8
- capability_name: Apache OpenWhisk Serverless Workflow
  capability_slug: serverless-workflow
  capability_url: https://capabilities.apis.io/capabilities/apache-openwhisk/serverless-workflow/
  consumed_api_count: 1
  operation_count: 5
  provider_name: Apache OpenWhisk
  provider_slug: apache-openwhisk
  tags:
  - Apache OpenWhisk
  - Serverless
  - Functions As A Service
  - Event Driven
  - Cloud Native
  tool_count: 10
- capability_name: Azure Function Apps Management
  capability_slug: azure-function-apps-management
  capability_url: https://capabilities.apis.io/capabilities/azure-function-apps/azure-function-apps-management/
  consumed_api_count: 1
  operation_count: 1
  provider_name: Azure Function Apps
  provider_slug: azure-function-apps
  tags:
  - Azure
  - Cloud
  - Management
  tool_count: 4
- capability_name: Cloudflare Serverless Compute
  capability_slug: serverless-compute
  capability_url: https://capabilities.apis.io/capabilities/cloudflare/serverless-compute/
  consumed_api_count: 4
  operation_count: 7
  provider_name: Cloudflare
  provider_slug: cloudflare
  tags:
  - Cloudflare
  - Serverless
  - Edge Computing
  - Deployment
  tool_count: 20
layout: category
name: Serverless Functions
provider_count: 5
related:
- container-orchestration
- ci-cd
short: Run code in response to events without managing servers.
slug: serverless
---
