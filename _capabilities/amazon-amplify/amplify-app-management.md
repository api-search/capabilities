---
categories: []
consumed_apis:
- amazon-amplify
description: Workflow capability for managing full-stack Amplify applications including app creation, branch management, and deployment workflows.
layout: capability
name: Amazon Amplify App Management
operations:
- description: List all Amplify apps.
  method: GET
  name: list-apps
  path: /v1/apps
personas: []
provider_name: Amazon Amplify
provider_slug: amazon-amplify
search_terms:
- list apps
- aws
- amplify
- amazon
- Frontend Developer
- DevOps Engineer
- developer building and deploying web and mobile frontends on aws amplify.
- list all amplify apps.
- mobile development
- web applications
- list all amazon amplify applications in the aws account.
- manage amplify apps, branches, and deployments.
- deployment
- frontend
- engineer managing ci/cd pipelines and deployments for amplify applications.
- create amplify app
- create a new amplify full-stack application connected to a code repository.
- list amplify apps
- hosting
- amplify application management.
- full stack
slug: amplify-app-management
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Amplify App Management\n  description: Workflow capability for managing full-stack Amplify applications including app creation, branch management, and deployment workflows.\n  tags:\n  - Amazon\n  - Amplify\n  - AWS\n  - Deployment\n  - Frontend\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: amazon-amplify\n    location: ./shared/amazon-amplify.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amplify-management-api\n    description: REST API for Amplify app management.\n    resources:\n    - path: /v1/apps\n      name: apps\n      description: Amplify application management.\n      operations:\n      - method: GET\n        name: list-apps\n        description: List all Amplify apps.\n        call: amazon-amplify.list-apps\n\
  \        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amplify-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Amplify app management.\n    tools:\n    - name: list-amplify-apps\n      description: List all Amazon Amplify applications in the AWS account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: amazon-amplify.list-apps\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-amplify-app\n      description: Create a new Amplify full-stack application connected to a code repository.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: amazon-amplify.create-app\n      with:\n        body: tools.body\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-amplify/refs/heads/main/capabilities/amplify-app-management.yaml
tags:
- Amazon
- Amplify
- AWS
- Deployment
- Frontend
tools:
- description: List all Amazon Amplify applications in the AWS account.
  hints:
    openWorld: false
    readOnly: true
  name: list-amplify-apps
- description: Create a new Amplify full-stack application connected to a code repository.
  hints:
    openWorld: false
    readOnly: false
  name: create-amplify-app
---
