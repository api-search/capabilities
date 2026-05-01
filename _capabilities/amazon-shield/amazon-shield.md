---
categories: []
consumed_apis:
- amazon-shield
description: Workflow capability for Amazon Shield. Enables automation of Amazon Shield resources for cloud operations teams.
layout: capability
name: Amazon Shield Operations
operations:
- description: List Amazon Shield resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Shield
provider_slug: amazon-shield
search_terms:
- cloud operations
- list resources
- aws
- security
- list amazon shield resources
- automation workflow for amazon shield
- amazon shield resources
- ddos protection
- amazon shield
- engineer managing amazon shield resources
- aws cloud resource management
- networking
slug: amazon-shield
source_filename: amazon-shield.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Shield Operations\n  description: Workflow capability for Amazon Shield. Enables automation of Amazon Shield resources for cloud operations teams.\n  tags:\n  - Amazon Shield\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - import: amazon-shield\n    location: ./shared/amazon-shield.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-shield-api\n    description: Unified REST API for Amazon Shield operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Shield resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Shield resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n \
  \   namespace: amazon-shield-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Shield operations.\n    tools:\n    - name: list-amazon-shield-resources\n      description: List Amazon Shield resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-shield/refs/heads/main/capabilities/amazon-shield.yaml
tags:
- Amazon Shield
- Cloud Operations
tools:
- description: List Amazon Shield resources
  hints:
    readOnly: true
  name: list-amazon-shield-resources
---
