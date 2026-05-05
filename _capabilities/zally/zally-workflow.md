---
categories: []
consumed_apis:
- api
description: Unified workflow capability composing Zally APIs.
layout: capability
name: Zally Workflow
operations:
- description: Zally API Violations
  method: POST
  name: post-api-violations
  path: /v1/api
- description: Zally Get Previous Generated Validation Result
  method: GET
  name: get-api-violationsexternal-id
  path: /v1/api
- description: Zally Suported Rules
  method: GET
  name: get-supported-rules
  path: /v1/api
- description: Zally Provides Query Capabilites for Linting Summaries and Automatically Computed Review Statistics.
  method: GET
  name: get-review-statistics
  path: /v1/api
personas: []
provider_name: Zally
provider_slug: zally
search_terms:
- zally suported rules
- api quality
- post api violations
- api get supported rules
- open source
- zally
- zally api violations
- get review statistics
- zally get previous generated validation result
- api post api violations
- openapi
- zally provides query capabilites for linting summaries and automatically computed review statistics.
- api design
- zalando
- operations for api
- api get review statistics
- get api violationsexternal id
- get supported rules
- api get api violationsexternal id
- api linting
slug: zally-workflow
source_filename: zally-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Zally Workflow\n  description: Unified workflow capability composing Zally APIs.\n  tags:\n    - Zally\n  created: '2026-05-03'\n  modified: '2026-05-03'\ncapability:\n  consumes:\n    - import: api\n      location: ./shared/api.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: zally-api\n      description: Unified REST API for Zally\n      resources:\n        - path: /v1/api\n          name: api\n          description: Operations for api\n          operations:\n            - method: POST\n              name: post-api-violations\n              description: Zally API Violations\n              call: api.post-api-violations\n            - method: GET\n              name: get-api-violationsexternal-id\n              description: Zally Get Previous Generated Validation Result\n              call: api.get-api-violationsexternal-id\n            - method: GET\n              name: get-supported-rules\n              description:\
  \ Zally Suported Rules\n              call: api.get-supported-rules\n            - method: GET\n              name: get-review-statistics\n              description: Zally Provides Query Capabilites for Linting Summaries and Automatically Computed Review Statistics.\n              call: api.get-review-statistics\n    - type: mcp\n      port: 9090\n      namespace: zally-mcp\n      transport: http\n      description: MCP server for Zally\n      tools:\n        - name: api-post-api-violations\n          description: Zally API Violations\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.post-api-violations\n        - name: api-get-api-violationsexternal-id\n          description: Zally Get Previous Generated Validation Result\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-api-violationsexternal-id\n        - name: api-get-supported-rules\n          description: Zally Suported Rules\n      \
  \    hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-supported-rules\n        - name: api-get-review-statistics\n          description: Zally Provides Query Capabilites for Linting Summaries and Automatically Computed Review Statistics.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-review-statistics\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zally/refs/heads/main/capabilities/zally-workflow.yaml
tags:
- Zally
tools:
- description: Zally API Violations
  hints:
    openWorld: true
    readOnly: false
  name: api-post-api-violations
- description: Zally Get Previous Generated Validation Result
  hints:
    openWorld: true
    readOnly: true
  name: api-get-api-violationsexternal-id
- description: Zally Suported Rules
  hints:
    openWorld: true
    readOnly: true
  name: api-get-supported-rules
- description: Zally Provides Query Capabilites for Linting Summaries and Automatically Computed Review Statistics.
  hints:
    openWorld: true
    readOnly: true
  name: api-get-review-statistics
---
