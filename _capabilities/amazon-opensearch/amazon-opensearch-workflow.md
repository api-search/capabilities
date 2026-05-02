---
categories: []
consumed_apis:
- opensearch
description: Workflow capability composing Amazon OpenSearch Service API APIs for developers and operators.
layout: capability
name: Amazon OpenSearch Service API API Workflow
operations:
- description: List Amazon OpenSearch Service API resources
  method: GET
  name: list-resources
  path: /v1/resources
personas: []
provider_name: Amazon OpenSearch Service API
provider_slug: amazon-opensearch
search_terms:
- list openapi.yml
- Developer
- core api workflow
- primary amazon opensearch service api resources
- search
- elasticsearch
- analytics
- list and manage openapi.yml resources
- developer using amazon opensearch service api apis
- list amazon opensearch service api resources
- amazon opensearch service api
- aws
- list resources
slug: amazon-opensearch-workflow
source_filename: amazon-opensearch-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon OpenSearch Service API API Workflow\n  description: Workflow capability composing Amazon OpenSearch Service API APIs for developers and operators.\n  tags:\n  - Amazon OpenSearch Service API\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - import: opensearch\n    location: ./shared/opensearch.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-opensearch-api\n    description: Unified REST API for Amazon OpenSearch Service API.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Primary Amazon OpenSearch Service API resources\n      operations:\n      - method: GET\n        name: list-resources\n        description: List Amazon OpenSearch Service API resources\n        call: openapi.yml.list\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \  - type: mcp\n    port: 9090\n    namespace: amazon-opensearch-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon OpenSearch Service API operations.\n    tools:\n    - name: list-openapi.yml\n      description: List and manage openapi.yml resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: openapi.yml.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-opensearch/refs/heads/main/capabilities/amazon-opensearch-workflow.yaml
tags:
- Amazon OpenSearch Service API
tools:
- description: List and manage openapi.yml resources
  hints:
    openWorld: true
    readOnly: true
  name: list-openapi.yml
---
