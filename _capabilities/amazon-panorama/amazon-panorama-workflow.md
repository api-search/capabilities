---
categories: []
consumed_apis:
- panorama
description: Workflow capability composing Amazon Panorama APIs for developers and operators.
layout: capability
name: Amazon Panorama API Workflow
operations:
- description: List Amazon Panorama resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Panorama
provider_slug: amazon-panorama
search_terms:
- list resources
- aws
- list and manage openapi.yml resources
- list openapi.yml
- cameras
- developer using amazon panorama apis
- Developer
- core api workflow
- edge ml
- list amazon panorama resources
- industrial iot
- primary amazon panorama resources
- amazon panorama
- computer vision
slug: amazon-panorama-workflow
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Panorama API Workflow\n  description: Workflow capability composing Amazon Panorama APIs for developers and operators.\n  tags:\n  - Amazon Panorama\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: panorama\n    location: ./shared/panorama.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-panorama-api\n    description: Unified REST API for Amazon Panorama.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon Panorama resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Panorama resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-panorama-mcp\n    transport: http\n \
  \   description: MCP server for AI-assisted Amazon Panorama operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-panorama/refs/heads/main/capabilities/amazon-panorama-workflow.yaml
tags:
- Amazon Panorama
- AWS
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
