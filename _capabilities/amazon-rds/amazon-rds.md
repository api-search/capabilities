---
api_specs:
- filename: amazon-rds-openapi.yml
  format: yaml
  label: amazon-rds
  slug: amazon-rds
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-rds/refs/heads/main/openapi/amazon-rds-openapi.yml
categories: []
consumed_apis:
- amazon-rds
description: Workflow capability for Amazon Rds. Enables automation of Amazon Rds resources for cloud operations teams.
layout: capability
name: Amazon Rds Operations
operations:
- description: List Amazon Rds resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon RDS
provider_slug: amazon-rds
search_terms:
- aws cloud resource management
- cloud databases
- amazon rds resources
- managed databases
- dbaas
- cloud operations
- amazon rds
- database service
- aws
- automation workflow for amazon rds
- engineer managing amazon rds resources
- list amazon rds resources
- list resources
- relational databases
slug: amazon-rds
source_filename: amazon-rds.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Rds Operations\n  description: Workflow capability for Amazon Rds. Enables automation of Amazon Rds resources for cloud operations teams.\n  tags:\n  - Amazon Rds\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - import: amazon-rds\n    location: ./shared/amazon-rds.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-rds-api\n    description: Unified REST API for Amazon Rds operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Rds resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Rds resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-rds-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted Amazon Rds operations.\n    tools:\n    - name: list-amazon-rds-resources\n      description: List Amazon Rds resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-rds/refs/heads/main/capabilities/amazon-rds.yaml
tags:
- Amazon Rds
- AWS
- Cloud Operations
tools:
- description: List Amazon Rds resources
  hints:
    readOnly: true
  name: list-amazon-rds-resources
---
