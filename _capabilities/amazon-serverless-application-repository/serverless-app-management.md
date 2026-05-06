---
categories:
- serverless
consumed_apis: []
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
- engineers who discover and deploy pre-built serverless applications from the repository
- lambda
- update metadata for a published serverless application
- devops
- developers who publish and share sam-based serverless applications
- serverless
- browse the serverless application repository catalog
- deploy a serverless application
- sam
- publish a new serverless application
- list versions
- deploy
- aws lambda-based application development, packaging, and distribution
- create version
- individual application management
- amazon serverless application repository
- deploy application
- list application versions
- serverless application catalog management
- application deployment via cloudformation
- application deployment pipeline management via cloudformation
- publish a new serverless application to the sar
- list all published versions of an application
- publish a new version of an existing application
- update application
- create application version
- get application details
- end-to-end serverless application lifecycle management including publishing, versioning, and deployment
- publish a new application version
- Platform Engineer
- get the sharing policy for a published application
- get application
- deploy a serverless application to your aws account
- application repository
- list applications
- browse the serverless application catalog
- publish application
- get details and metadata for a serverless application
- application version management
- get application policy
- Serverless Developer
slug: serverless-app-management
source_filename: serverless-app-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon SAR Serverless App Management\n  description: Unified capability for publishing, discovering, and deploying serverless applications via the AWS Serverless\n    Application Repository. Used by Serverless Developers and Platform Engineers.\n  tags:\n  - Amazon Serverless Application Repository\n  - Serverless\n  - Lambda\n  - SAM\n  - DevOps\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-serverless-application-repository\n    baseUri: https://serverlessrepo.us-east-1.amazonaws.com\n    description: Amazon Serverless Application Repository REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 Credential={{AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n\
  \    - name: applications\n      path: /applications\n      description: Application management operations\n      operations:\n      - name: list-applications\n        method: GET\n        description: Lists applications owned by the requester\n        inputParameters:\n        - name: maxItems\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application\n        method: POST\n        description: Creates an application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Gets\
  \ the specified application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: The application ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-application\n        method: PATCH\n        description: Updates the specified application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: The application ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-application\n        method: DELETE\n        description: Deletes the specified application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description:\
  \ The application ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application-version\n        method: POST\n        description: Creates an application version\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: The application ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-application-versions\n        method: GET\n        description: Lists versions for the specified application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: The application ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: create-changeset\n        method: POST\n        description: Creates an AWS CloudFormation change set for the given application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: The application ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application-policy\n        method: GET\n        description: Retrieves the policy for the application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: The application ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-application-policy\n        method: PUT\n        description: Sets the permission policy for an application\n        inputParameters:\n\
  \        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: The application ARN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: serverless-app-management-api\n    description: Unified REST API for Amazon SAR serverless application lifecycle management.\n    resources:\n    - path: /v1/applications\n      name: applications\n      description: Serverless application catalog management\n      operations:\n      - method: GET\n        name: list-applications\n        description: Browse the serverless application catalog\n        call: amazon-serverless-application-repository.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: publish-application\n        description: Publish a new serverless application\n      \
  \  call: amazon-serverless-application-repository.create-application\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{applicationId}\n      name: application\n      description: Individual application management\n      operations:\n      - method: GET\n        name: get-application\n        description: Get application details\n        call: amazon-serverless-application-repository.get-application\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{applicationId}/versions\n      name: application-versions\n      description: Application version management\n      operations:\n      - method: GET\n        name: list-versions\n        description: List application versions\n        call: amazon-serverless-application-repository.list-application-versions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-version\n  \
  \      description: Publish a new application version\n        call: amazon-serverless-application-repository.create-application-version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{applicationId}/deploy\n      name: application-deployment\n      description: Application deployment via CloudFormation\n      operations:\n      - method: POST\n        name: deploy\n        description: Deploy a serverless application\n        call: amazon-serverless-application-repository.create-changeset\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: serverless-app-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon SAR serverless application lifecycle management.\n    tools:\n    - name: list-applications\n      description: Browse the serverless application repository catalog\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n      call: amazon-serverless-application-repository.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-application\n      description: Publish a new serverless application to the SAR\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-serverless-application-repository.create-application\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application\n      description: Get details and metadata for a serverless application\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-serverless-application-repository.get-application\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-application\n      description: Update metadata for a published serverless application\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-serverless-application-repository.update-application\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-application-versions\n      description: List all published versions of an application\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-serverless-application-repository.list-application-versions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-application-version\n      description: Publish a new version of an existing application\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-serverless-application-repository.create-application-version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-application\n      description: Deploy a serverless application to your AWS account\n      hints:\n        readOnly: false\n        idempotent: false\n      call: amazon-serverless-application-repository.create-changeset\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: get-application-policy\n      description: Get the sharing policy for a published application\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amazon-serverless-application-repository.get-application-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
