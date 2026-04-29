---
api_specs:
- filename: amazon-quicksight-openapi.yml
  format: yaml
  label: amazon-quicksight
  slug: amazon-quicksight
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-quicksight/refs/heads/main/openapi/amazon-quicksight-openapi.yml
categories: []
consumed_apis:
- amazon-quicksight
description: Workflow capability for Amazon Quicksight. Enables automation of Amazon Quicksight resources for cloud operations teams.
layout: capability
name: Amazon Quicksight Operations
operations:
- description: List Amazon Quicksight resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon QuickSight
provider_slug: amazon-quicksight
search_terms:
- machine learning
- reporting
- aws cloud resource management
- amazon quicksight resources
- list amazon quicksight resources
- automation workflow for amazon quicksight
- bi
- list resources
- amazon quicksight
- visualization
- dashboards
- business intelligence
- cloud operations
- engineer managing amazon quicksight resources
- aws
- analytics
slug: amazon-quicksight
source_filename: amazon-quicksight.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Quicksight Operations\n  description: Workflow capability for Amazon Quicksight. Enables automation of Amazon Quicksight resources for cloud operations teams.\n  tags:\n  - Amazon Quicksight\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - import: amazon-quicksight\n    location: ./shared/amazon-quicksight.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-quicksight-api\n    description: Unified REST API for Amazon Quicksight operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Quicksight resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Quicksight resources\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-quicksight-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Quicksight operations.\n    tools:\n    - name: list-amazon-quicksight-resources\n      description: List Amazon Quicksight resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-quicksight/refs/heads/main/capabilities/amazon-quicksight.yaml
tags:
- Amazon Quicksight
- AWS
- Cloud Operations
tools:
- description: List Amazon Quicksight resources
  hints:
    readOnly: true
  name: list-amazon-quicksight-resources
---
