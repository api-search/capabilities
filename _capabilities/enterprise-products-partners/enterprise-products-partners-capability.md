---
categories: []
consumed_apis: []
description: Enterprise Products Partners provides midstream energy services including pipeline operations, natural gas processing, and energy logistics across North America.
layout: capability
name: Enterprise Products Partners Pipeline Operations API
operations:
- description: Get Pipelines
  method: GET
  name: getpipelines
  path: /pipelines
- description: Get Pipeline by ID
  method: GET
  name: getpipelinebyid
  path: /pipelines/{pipelineId}
- description: Get Capacity Information
  method: GET
  name: getcapacity
  path: /capacity
personas: []
provider_name: Enterprise Products Partners
provider_slug: enterprise-products-partners
search_terms:
- midstream
- pipelines
- products
- get pipelines
- getpipelines
- api
- get pipeline by id
- getcapacity
- get capacity information
- enterprise
- partners
- energy
- natural gas
- getpipelinebyid
slug: enterprise-products-partners-capability
source_filename: enterprise-products-partners-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Enterprise Products Partners Pipeline Operations API\n  description: Enterprise Products Partners provides midstream energy services including pipeline operations, natural gas\n    processing, and energy logistics across North America.\n  tags:\n  - Enterprise\n  - Products\n  - Partners\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: enterprise-products-partners\n    baseUri: https://api.enterpriseproducts.com\n    description: Enterprise Products Partners Pipeline Operations API HTTP API.\n    resources:\n    - name: pipelines\n      path: /pipelines\n      operations:\n      - name: getpipelines\n        method: GET\n        description: Get Pipelines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines-pipelineid\n      path: /pipelines/{pipelineId}\n      operations:\n\
  \      - name: getpipelinebyid\n        method: GET\n        description: Get Pipeline by ID\n        inputParameters:\n        - name: pipelineId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: capacity\n      path: /capacity\n      operations:\n      - name: getcapacity\n        method: GET\n        description: Get Capacity Information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: enterprise-products-partners-rest\n    description: REST adapter for Enterprise Products Partners Pipeline Operations API.\n    resources:\n    - path: /pipelines\n      name: getpipelines\n      operations:\n      - method: GET\n        name: getpipelines\n        description: Get Pipelines\n        call: enterprise-products-partners.getpipelines\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pipelines/{pipelineId}\n      name: getpipelinebyid\n      operations:\n      - method: GET\n        name: getpipelinebyid\n        description: Get Pipeline by ID\n        call: enterprise-products-partners.getpipelinebyid\n        with:\n          pipelineId: rest.pipelineId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /capacity\n      name: getcapacity\n      operations:\n      - method: GET\n        name: getcapacity\n        description: Get Capacity Information\n        call: enterprise-products-partners.getcapacity\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: enterprise-products-partners-mcp\n    transport: http\n    description: MCP adapter for Enterprise Products Partners Pipeline Operations API for AI agent use.\n    tools:\n    - name: getpipelines\n      description: Get\
  \ Pipelines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: enterprise-products-partners.getpipelines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpipelinebyid\n      description: Get Pipeline by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: enterprise-products-partners.getpipelinebyid\n      with:\n        pipelineId: tools.pipelineId\n      inputParameters:\n      - name: pipelineId\n        type: string\n        description: pipelineId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcapacity\n      description: Get Capacity Information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: enterprise-products-partners.getcapacity\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/enterprise-products-partners/refs/heads/main/capabilities/enterprise-products-partners-capability.yaml
tags:
- Enterprise
- Products
- Partners
- API
tools:
- description: Get Pipelines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpipelines
- description: Get Pipeline by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpipelinebyid
- description: Get Capacity Information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcapacity
---
