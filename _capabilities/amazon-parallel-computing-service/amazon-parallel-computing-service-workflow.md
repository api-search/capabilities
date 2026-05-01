---
categories: []
consumed_apis:
- pcs
description: Workflow capability composing Amazon Parallel Computing Service APIs for developers and operators.
layout: capability
name: Amazon Parallel Computing Service API Workflow
operations:
- description: List Amazon Parallel Computing Service resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon Parallel Computing Service
provider_slug: amazon-parallel-computing-service
search_terms:
- list resources
- developer using amazon parallel computing service apis
- aws
- list and manage openapi.yml resources
- hpc
- parallel computing
- list amazon parallel computing service resources
- primary amazon parallel computing service resources
- amazon parallel computing service
- high performance computing
- scientific computing
- core api workflow
- Developer
- list openapi.yml
slug: amazon-parallel-computing-service-workflow
source_filename: amazon-parallel-computing-service-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Parallel Computing Service API Workflow\n  description: Workflow capability composing Amazon Parallel Computing Service APIs for developers and operators.\n  tags:\n  - Amazon Parallel Computing Service\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: pcs\n    location: ./shared/pcs.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-parallel-computing-service-api\n    description: Unified REST API for Amazon Parallel Computing Service.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon Parallel Computing Service resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon Parallel Computing Service resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-parallel-computing-service-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Parallel Computing Service operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-parallel-computing-service/refs/heads/main/capabilities/amazon-parallel-computing-service-workflow.yaml
tags:
- Amazon Parallel Computing Service
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
