---
api_specs:
- filename: amazon-app-runner-openapi.yml
  format: yaml
  label: amazon-app-runner
  slug: amazon-app-runner
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-app-runner/refs/heads/main/openapi/amazon-app-runner-openapi.yml
categories: []
consumed_apis:
- amazon-app-runner
description: Workflow for managing Amazon App Runner API resources.
layout: capability
name: App Runner Management
operations:
- description: List resources.
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon App Runner
provider_slug: amazon-app-runner
search_terms:
- list resources
- amazon
- manage amazon app runner api resources.
- DevOps Engineer
- engineer automating deployments using app runner api.
- developer deploying web apis and services on app runner.
- aws
- list resources.
- web applications
- Backend Developer
- containers
- managed service
- serverless
- ci/cd
- list amazon app runner api resources.
- deployment
slug: app-runner-management
source_filename: app-runner-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: App Runner Management\n  description: Workflow for managing Amazon App Runner API resources.\n  tags:\n  - Amazon\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: amazon-app-runner\n    location: ./shared/amazon-app-runner.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: app-runner-management-api\n    resources:\n    - path: /v1/resources\n      name: resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List resources.\n        call: amazon-app-runner.list-resources\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: app-runner-management-mcp\n    transport: http\n    tools:\n    - name:\
  \ list-resources\n      description: List Amazon App Runner API resources.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: amazon-app-runner.list-resources\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-app-runner/refs/heads/main/capabilities/app-runner-management.yaml
tags:
- Amazon
- AWS
tools:
- description: List Amazon App Runner API resources.
  hints:
    openWorld: false
    readOnly: true
  name: list-resources
---
