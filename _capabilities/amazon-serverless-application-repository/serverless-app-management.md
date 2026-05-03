---
api_specs:
- filename: amazon-serverless-application-repository-openapi.yml
  format: yaml
  label: amazon-serverless-application-repository
  slug: amazon-serverless-application-repository
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-serverless-application-repository/refs/heads/main/openapi/amazon-serverless-application-repository-openapi.yml
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
- list versions
- publish a new serverless application
- list application versions
- update metadata for a published serverless application
- get details and metadata for a serverless application
- get application details
- update application
- Platform Engineer
- aws lambda-based application development, packaging, and distribution
- developers who publish and share sam-based serverless applications
- devops
- engineers who discover and deploy pre-built serverless applications from the repository
- deploy a serverless application
- application deployment via cloudformation
- get application
- browse the serverless application catalog
- list all published versions of an application
- Serverless Developer
- individual application management
- browse the serverless application repository catalog
- publish a new version of an existing application
- deploy a serverless application to your aws account
- serverless application catalog management
- end-to-end serverless application lifecycle management including publishing, versioning, and deployment
- publish a new serverless application to the sar
- deploy application
- publish a new application version
- get the sharing policy for a published application
- create application version
- serverless
- application deployment pipeline management via cloudformation
- amazon serverless application repository
- application version management
- lambda
- deploy
- get application policy
- application repository
- create version
- sam
- list applications
- publish application
slug: serverless-app-management
source_filename: serverless-app-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon SAR Serverless App Management\"\n  description: \"Unified capability for publishing, discovering, and deploying serverless applications via the AWS Serverless Application Repository. Used by Serverless Developers and Platform Engineers.\"\n  tags:\n    - Amazon Serverless Application Repository\n    - Serverless\n    - Lambda\n    - SAM\n    - DevOps\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-serverless-application-repository\n      location: ./shared/amazon-serverless-application-repository.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: serverless-app-management-api\n      description: \"Unified REST API for Amazon SAR serverless application lifecycle management.\"\n  \
  \    resources:\n        - path: /v1/applications\n          name: applications\n          description: \"Serverless application catalog management\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"Browse the serverless application catalog\"\n              call: \"amazon-serverless-application-repository.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: publish-application\n              description: \"Publish a new serverless application\"\n              call: \"amazon-serverless-application-repository.create-application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{applicationId}\n          name: application\n          description: \"Individual application management\"\n          operations:\n            - method:\
  \ GET\n              name: get-application\n              description: \"Get application details\"\n              call: \"amazon-serverless-application-repository.get-application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{applicationId}/versions\n          name: application-versions\n          description: \"Application version management\"\n          operations:\n            - method: GET\n              name: list-versions\n              description: \"List application versions\"\n              call: \"amazon-serverless-application-repository.list-application-versions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-version\n              description: \"Publish a new application version\"\n              call: \"amazon-serverless-application-repository.create-application-version\"\n   \
  \           outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{applicationId}/deploy\n          name: application-deployment\n          description: \"Application deployment via CloudFormation\"\n          operations:\n            - method: POST\n              name: deploy\n              description: \"Deploy a serverless application\"\n              call: \"amazon-serverless-application-repository.create-changeset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: serverless-app-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon SAR serverless application lifecycle management.\"\n      tools:\n        - name: list-applications\n          description: \"Browse the serverless application repository catalog\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"amazon-serverless-application-repository.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-application\n          description: \"Publish a new serverless application to the SAR\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-serverless-application-repository.create-application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application\n          description: \"Get details and metadata for a serverless application\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-serverless-application-repository.get-application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-application\n          description: \"Update metadata for a published serverless application\"\
  \n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-serverless-application-repository.update-application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-application-versions\n          description: \"List all published versions of an application\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-serverless-application-repository.list-application-versions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-application-version\n          description: \"Publish a new version of an existing application\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-serverless-application-repository.create-application-version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n     \
  \   - name: deploy-application\n          description: \"Deploy a serverless application to your AWS account\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"amazon-serverless-application-repository.create-changeset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application-policy\n          description: \"Get the sharing policy for a published application\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amazon-serverless-application-repository.get-application-policy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-serverless-application-repository/refs/heads/main/capabilities/serverless-app-management.yaml
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
