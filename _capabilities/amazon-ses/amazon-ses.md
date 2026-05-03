---
api_specs:
- filename: amazon-ses-openapi.yml
  format: yaml
  label: amazon-ses
  slug: amazon-ses
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-ses/refs/heads/main/openapi/amazon-ses-openapi.yml
categories: []
consumed_apis:
- amazon-ses
description: Workflow capability for Amazon Ses. Enables automation of Amazon Ses resources for cloud operations teams.
layout: capability
name: Amazon Ses Operations
operations:
- description: List Amazon Ses resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon SES
provider_slug: amazon-ses
search_terms:
- aws cloud resource management
- list amazon ses resources
- email deliverability
- email service
- aws
- marketing email
- amazon ses
- smtp
- automation workflow for amazon ses
- email
- transactional email
- notifications
- amazon ses resources
- cloud operations
- engineer managing amazon ses resources
- list resources
slug: amazon-ses
source_filename: amazon-ses.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Ses Operations\n  description: Workflow capability for Amazon Ses. Enables automation of Amazon Ses resources for cloud operations teams.\n  tags:\n  - Amazon Ses\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - import: amazon-ses\n    location: ./shared/amazon-ses.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-ses-api\n    description: Unified REST API for Amazon Ses operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon Ses resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Ses resources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-ses-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted Amazon Ses operations.\n    tools:\n    - name: list-amazon-ses-resources\n      description: List Amazon Ses resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ses/refs/heads/main/capabilities/amazon-ses.yaml
tags:
- Amazon Ses
- Cloud Operations
tools:
- description: List Amazon Ses resources
  hints:
    readOnly: true
  name: list-amazon-ses-resources
---
