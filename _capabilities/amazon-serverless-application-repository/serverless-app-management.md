---
consumed_apis:
- amazon-serverless-application-repository
description: Unified capability for publishing, discovering, and deploying serverless applications via the AWS Serverless Application Repository. Used by Serverless Developers and Platform Engineers.
layout: capability
name: Amazon SAR Serverless App Management
operations:
- description: Browse the serverless application catalog
  method: GET
  name: list-applications
  path: /v1/applications
- description: Publish a new serverless application
  method: POST
  name: publish-application
  path: /v1/applications
- description: Get application details
  method: GET
  name: get-application
  path: /v1/applications/{applicationId}
- description: List application versions
  method: GET
  name: list-versions
  path: /v1/applications/{applicationId}/versions
- description: Publish a new application version
  method: POST
  name: create-version
  path: /v1/applications/{applicationId}/versions
- description: Deploy a serverless application
  method: POST
  name: deploy
  path: /v1/applications/{applicationId}/deploy
personas: []
provider_name: Amazon Serverless Application Repository
provider_slug: amazon-serverless-application-repository
search_terms:
- deploy a serverless application
- end-to-end serverless application lifecycle management including publishing, versioning, and deployment
- individual application management
- get application
- list versions
- serverless
- get the sharing policy for a published application
- deploy application
- list all published versions of an application
- Platform Engineer
- sam
- browse the serverless application repository catalog
- engineers who discover and deploy pre-built serverless applications from the repository
- update application
- publish a new application version
- devops
- get application details
- create application version
- list applications
- deploy
- publish a new serverless application to the sar
- publish application
- list application versions
- create version
- update metadata for a published serverless application
- amazon serverless application repository
- serverless application catalog management
- developers who publish and share sam-based serverless applications
- application deployment via cloudformation
- aws lambda-based application development, packaging, and distribution
- get application policy
- publish a new version of an existing application
- application version management
- deploy a serverless application to your aws account
- application deployment pipeline management via cloudformation
- aws
- lambda
- Serverless Developer
- browse the serverless application catalog
- publish a new serverless application
- application repository
- get details and metadata for a serverless application
slug: serverless-app-management
tags:
- Amazon Serverless Application Repository
- Serverless
- Lambda
- SAM
- DevOps
tools:
- description: Browse the serverless application repository catalog
  hints:
    idempotent: true
    readOnly: true
  name: list-applications
- description: Publish a new serverless application to the SAR
  hints:
    idempotent: false
    readOnly: false
  name: publish-application
- description: Get details and metadata for a serverless application
  hints:
    idempotent: true
    readOnly: true
  name: get-application
- description: Update metadata for a published serverless application
  hints:
    idempotent: false
    readOnly: false
  name: update-application
- description: List all published versions of an application
  hints:
    idempotent: true
    readOnly: true
  name: list-application-versions
- description: Publish a new version of an existing application
  hints:
    idempotent: false
    readOnly: false
  name: create-application-version
- description: Deploy a serverless application to your AWS account
  hints:
    idempotent: false
    readOnly: false
  name: deploy-application
- description: Get the sharing policy for a published application
  hints:
    idempotent: true
    readOnly: true
  name: get-application-policy
---
