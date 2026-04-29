---
categories: []
consumed_apis:
- amazon-robomaker
description: Workflow capability for Amazon Robomaker. Enables automation of Amazon Robomaker resources for cloud operations teams.
layout: capability
name: Amazon Robomaker Operations
operations:
- description: List Amazon Robomaker resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon RoboMaker
provider_slug: amazon-robomaker
search_terms:
- list resources
- aws
- amazon robomaker resources
- aws cloud resource management
- simulation
- cloud operations
- automation workflow for amazon robomaker
- robotics
- list amazon robomaker resources
- amazon robomaker
- engineer managing amazon robomaker resources
slug: amazon-robomaker
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Robomaker Operations\n  description: Workflow capability for Amazon Robomaker. Enables automation of Amazon Robomaker resources for cloud operations teams.\n  tags:\n  - Amazon Robomaker\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - import: amazon-robomaker\n    location: ./shared/amazon-robomaker.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-robomaker-api\n    description: Unified REST API for Amazon Robomaker operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Robomaker resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Robomaker resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  -\
  \ type: mcp\n    port: 9090\n    namespace: amazon-robomaker-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Robomaker operations.\n    tools:\n    - name: list-amazon-robomaker-resources\n      description: List Amazon Robomaker resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-robomaker/refs/heads/main/capabilities/amazon-robomaker.yaml
tags:
- Amazon Robomaker
- AWS
- Cloud Operations
tools:
- description: List Amazon Robomaker resources
  hints:
    readOnly: true
  name: list-amazon-robomaker-resources
---
