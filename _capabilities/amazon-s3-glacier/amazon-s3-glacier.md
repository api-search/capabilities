---
categories: []
consumed_apis:
- amazon-s3-glacier
description: Workflow capability for Amazon S3 Glacier. Enables automation of Amazon S3 Glacier resources for cloud operations teams.
layout: capability
name: Amazon S3 Glacier Operations
operations:
- description: List Amazon S3 Glacier resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon S3 Glacier
provider_slug: amazon-s3-glacier
search_terms:
- list resources
- aws
- aws cloud resource management
- archive
- backup
- automation workflow for amazon s3 glacier
- cloud operations
- amazon s3 glacier
- engineer managing amazon s3 glacier resources
- list amazon s3 glacier resources
- storage
- amazon s3 glacier resources
slug: amazon-s3-glacier
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon S3 Glacier Operations\n  description: Workflow capability for Amazon S3 Glacier. Enables automation of Amazon S3 Glacier resources for cloud operations teams.\n  tags:\n  - Amazon S3 Glacier\n  - AWS\n  - Cloud Operations\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY: AWS_ACCESS_KEY\n    AWS_SECRET_KEY: AWS_SECRET_KEY\ncapability:\n  consumes:\n  - import: amazon-s3-glacier\n    location: ./shared/amazon-s3-glacier.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-s3-glacier-api\n    description: Unified REST API for Amazon S3 Glacier operations.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon S3 Glacier resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon S3 Glacier resources\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-s3-glacier-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon S3 Glacier operations.\n    tools:\n    - name: list-amazon-s3-glacier-resources\n      description: List Amazon S3 Glacier resources\n      hints:\n        readOnly: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-s3-glacier/refs/heads/main/capabilities/amazon-s3-glacier.yaml
tags:
- Amazon S3 Glacier
- AWS
- Cloud Operations
tools:
- description: List Amazon S3 Glacier resources
  hints:
    readOnly: true
  name: list-amazon-s3-glacier-resources
---
