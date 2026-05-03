---
categories: []
consumed_apis:
- opensearch_service
description: Workflow capability composing Amazon OpenSearch Service APIs for developers and operators.
layout: capability
name: Amazon OpenSearch Service API Workflow
operations:
- description: List Amazon OpenSearch Service resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon OpenSearch Service
provider_slug: amazon-opensearch-service
search_terms:
- opensearch
- list amazon opensearch service resources
- list openapi.yml
- Developer
- developer using amazon opensearch service apis
- list resources
- amazon opensearch service
- core api workflow
- log analytics
- full-text search
- primary amazon opensearch service resources
- elasticsearch
- analytics
- aws
- search
- list and manage openapi.yml resources
slug: amazon-opensearch-service-workflow
source_filename: amazon-opensearch-service-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon OpenSearch Service API Workflow\n  description: Workflow capability composing Amazon OpenSearch Service APIs for developers and operators.\n  tags:\n  - Amazon OpenSearch Service\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: opensearch_service\n    location: ./shared/opensearch-service.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-opensearch-service-api\n    description: Unified REST API for Amazon OpenSearch Service.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon OpenSearch Service resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon OpenSearch Service resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \  - type: mcp\n    port: 9090\n    namespace: amazon-opensearch-service-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon OpenSearch Service operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-opensearch-service/refs/heads/main/capabilities/amazon-opensearch-service-workflow.yaml
tags:
- Amazon OpenSearch Service
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
