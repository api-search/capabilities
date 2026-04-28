---
categories:
- serverless
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
- publish a new version of an existing application
- aws lambda-based application development, packaging, and distribution
- engineers who discover and deploy pre-built serverless applications from the repository
- devops
- application deployment via cloudformation
- create version
- developers who publish and share sam-based serverless applications
- lambda
- create application version
- deploy a serverless application
- publish a new serverless application
- publish application
- sam
- individual application management
- get details and metadata for a serverless application
- list application versions
- list all published versions of an application
- update metadata for a published serverless application
- browse the serverless application catalog
- deploy
- list applications
- end-to-end serverless application lifecycle management including publishing, versioning, and deployment
- serverless application catalog management
- application version management
- Platform Engineer
- application repository
- deploy a serverless application to your aws account
- browse the serverless application repository catalog
- get the sharing policy for a published application
- Serverless Developer
- amazon serverless application repository
- publish a new serverless application to the sar
- serverless
- update application
- deploy application
- application deployment pipeline management via cloudformation
- publish a new application version
- get application policy
- get application details
- aws
- get application
- list versions
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
