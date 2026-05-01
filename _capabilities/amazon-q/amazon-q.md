---
api_specs:
- filename: amazon-q-openapi.yml
  format: yaml
  label: amazon-q
  slug: amazon-q
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-q/refs/heads/main/openapi/amazon-q-openapi.yml
categories: []
consumed_apis:
- amazon-q
description: Workflow capability for Amazon Q. Enables automation of Amazon Q resources for cloud operations teams.
layout: capability
name: Amazon Q Operations
operations:
- description: List Amazon Q resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Q
provider_slug: amazon-q
search_terms:
- engineer managing amazon q resources
- aws cloud resource management
- automation workflow for amazon q
- amazon q
- assistant
- enterprise
- generative ai
- artificial intelligence
- cloud operations
- aws
- list amazon q resources
- list resources
- amazon q resources
slug: amazon-q
source_filename: amazon-q.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Q Operations\n  description: Workflow capability for Amazon Q. Enables automation of Amazon Q resources for cloud operations teams.\n  tags:\n  - Amazon Q\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - import: amazon-q\n    location: ./shared/amazon-q.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-q-api\n    description: Unified REST API for Amazon Q operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Q resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Q resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-q-mcp\n    transport: http\n \
  \   description: MCP server for AI-assisted Amazon Q operations.\n    tools:\n    - name: list-amazon-q-resources\n      description: List Amazon Q resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-q/refs/heads/main/capabilities/amazon-q.yaml
tags:
- Amazon Q
- AWS
- Cloud Operations
tools:
- description: List Amazon Q resources
  hints:
    readOnly: true
  name: list-amazon-q-resources
---
