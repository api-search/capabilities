---
api_specs:
- filename: amazon-resource-explorer-openapi.yml
  format: yaml
  label: amazon-resource-explorer
  slug: amazon-resource-explorer
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-resource-explorer/refs/heads/main/openapi/amazon-resource-explorer-openapi.yml
categories: []
consumed_apis:
- amazon-resource-explorer
description: Workflow capability for Amazon Resource Explorer. Enables automation of Amazon Resource Explorer resources for cloud operations teams.
layout: capability
name: Amazon Resource Explorer Operations
operations:
- description: List Amazon Resource Explorer resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Resource Explorer
provider_slug: amazon-resource-explorer
search_terms:
- list resources
- operations
- cloud operations
- engineer managing amazon resource explorer resources
- aws
- list amazon resource explorer resources
- amazon resource explorer resources
- automation workflow for amazon resource explorer
- aws cloud resource management
- resource management
- amazon resource explorer
- inventory
- discovery
slug: amazon-resource-explorer
source_filename: amazon-resource-explorer.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Resource Explorer Operations\n  description: Workflow capability for Amazon Resource Explorer. Enables automation of Amazon Resource Explorer resources for cloud operations teams.\n  tags:\n  - Amazon Resource Explorer\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - import: amazon-resource-explorer\n    location: ./shared/amazon-resource-explorer.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-resource-explorer-api\n    description: Unified REST API for Amazon Resource Explorer operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Resource Explorer resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Resource Explorer resources\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-resource-explorer-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Resource Explorer operations.\n    tools:\n    - name: list-amazon-resource-explorer-resources\n      description: List Amazon Resource Explorer resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-resource-explorer/refs/heads/main/capabilities/amazon-resource-explorer.yaml
tags:
- Amazon Resource Explorer
- AWS
- Cloud Operations
tools:
- description: List Amazon Resource Explorer resources
  hints:
    readOnly: true
  name: list-amazon-resource-explorer-resources
---
