---
categories: []
consumed_apis: []
description: API for partially evaluating Rego queries in OPA (Open Policy Agent).
layout: capability
name: Compile API
operations:
- description: Partially Evaluate a Query
  method: POST
  name: post-v1-compile
  path: /v1/compile
personas: []
provider_name: Open Policy Agent
provider_slug: open-policy-agent
search_terms:
- partially evaluate a query
- agent
- post v1 compile
- policy
- api
- open
- policies
- standards
slug: open-policy-agent-capability
source_filename: open-policy-agent-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Compile API\n  description: API for partially evaluating Rego queries in OPA (Open Policy Agent).\n  tags:\n  - Open\n  - Policy\n  - Agent\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: open-policy-agent\n    baseUri: https://api.example.com\n    description: Compile API HTTP API.\n    resources:\n    - name: v1-compile\n      path: /v1/compile\n      operations:\n      - name: post-v1-compile\n        method: POST\n        description: Partially Evaluate a Query\n        inputParameters:\n        - name: pretty\n          in: query\n          type: boolean\n          description: Format response for human readability.\n        - name: explain\n          in: query\n          type: string\n          description: Return query explanation.\n        - name: metrics\n          in: query\n          type: boolean\n          description: Return performance metrics.\n     \
  \   - name: instrument\n          in: query\n          type: boolean\n          description: Instrument query evaluation and return additional metrics.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: open-policy-agent-rest\n    description: REST adapter for Compile API.\n    resources:\n    - path: /v1/compile\n      name: post-v1-compile\n      operations:\n      - method: POST\n        name: post-v1-compile\n        description: Partially Evaluate a Query\n        call: open-policy-agent.post-v1-compile\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: open-policy-agent-mcp\n    transport: http\n    description: MCP adapter for Compile API for AI agent use.\n    tools:\n    - name: post-v1-compile\n      description: Partially Evaluate a Query\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: open-policy-agent.post-v1-compile\n      with:\n        pretty: tools.pretty\n        explain: tools.explain\n        metrics: tools.metrics\n        instrument: tools.instrument\n      inputParameters:\n      - name: pretty\n        type: boolean\n        description: Format response for human readability.\n      - name: explain\n        type: string\n        description: Return query explanation.\n      - name: metrics\n        type: boolean\n        description: Return performance metrics.\n      - name: instrument\n        type: boolean\n        description: Instrument query evaluation and return additional metrics.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/open-policy-agent/refs/heads/main/capabilities/open-policy-agent-capability.yaml
tags:
- Open
- Policy
- Agent
- API
tools:
- description: Partially Evaluate a Query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-compile
---
