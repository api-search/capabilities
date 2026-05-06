---
categories: []
consumed_apis: []
description: 'The Jentic API enables AI agents to dynamically discover, load, and execute APIs and workflows through a standards-based platform. The API provides three core operations: searching the Jentic catalog for relevant APIs and workflows using natural language queries, loading detailed execution information including input schemas and authentication requirements, and executing operations with managed authentication and credential injection. Built on OpenAPI and Arazzo specifications, the platform offers access to over 1500 APIs and 2000 agent-ready workflows with secure, server-side credential manag'
layout: capability
name: Jentic API
operations:
- description: Jentic Register a new account
  method: POST
  name: registeraccount
  path: /auth/register
- description: Jentic Search for APIs and workflows
  method: POST
  name: searchapis
  path: /agents/search
- description: Jentic Load execution information for operations
  method: POST
  name: loadexecutioninfo
  path: /agents/load
- description: Jentic Execute an API operation or workflow
  method: POST
  name: executeoperation
  path: /agents/execute
personas: []
provider_name: Jentic
provider_slug: jentic
search_terms:
- integrations
- loadexecutioninfo
- openapi
- mcp
- api
- ai agents
- jentic execute an api operation or workflow
- jentic load execution information for operations
- arazzo
- workflows
- jentic
- jentic register a new account
- registeraccount
- searchapis
- executeoperation
- jentic search for apis and workflows
slug: jentic-capability
source_filename: jentic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Jentic API\n  description: 'The Jentic API enables AI agents to dynamically discover, load, and execute APIs and workflows through a standards-based\n    platform. The API provides three core operations: searching the Jentic catalog for relevant APIs and workflows using natural\n    language queries, loading detailed execution information including input schemas and authentication requirements, and\n    executing operations with managed authentication and credential injection. Built on OpenAPI and Arazzo specifications,\n    the platform offers access to over 1500 APIs and 2000 agent-ready workflows with secure, server-side credential manag'\n  tags:\n  - Jentic\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jentic\n    baseUri: https://api.jentic.com/api/v1\n    description: Jentic API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name:\
  \ X-JENTIC-API-KEY\n      value: '{{JENTIC_TOKEN}}'\n    resources:\n    - name: auth-register\n      path: /auth/register\n      operations:\n      - name: registeraccount\n        method: POST\n        description: Jentic Register a new account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents-search\n      path: /agents/search\n      operations:\n      - name: searchapis\n        method: POST\n        description: Jentic Search for APIs and workflows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents-load\n      path: /agents/load\n      operations:\n      - name: loadexecutioninfo\n        method: POST\n        description: Jentic Load execution information for operations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: agents-execute\n      path: /agents/execute\n      operations:\n      - name: executeoperation\n        method: POST\n        description: Jentic Execute an API operation or workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jentic-rest\n    description: REST adapter for Jentic API.\n    resources:\n    - path: /auth/register\n      name: registeraccount\n      operations:\n      - method: POST\n        name: registeraccount\n        description: Jentic Register a new account\n        call: jentic.registeraccount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agents/search\n      name: searchapis\n      operations:\n      - method: POST\n        name: searchapis\n        description: Jentic Search for APIs and workflows\n        call: jentic.searchapis\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /agents/load\n      name: loadexecutioninfo\n      operations:\n      - method: POST\n        name: loadexecutioninfo\n        description: Jentic Load execution information for operations\n        call: jentic.loadexecutioninfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agents/execute\n      name: executeoperation\n      operations:\n      - method: POST\n        name: executeoperation\n        description: Jentic Execute an API operation or workflow\n        call: jentic.executeoperation\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jentic-mcp\n    transport: http\n    description: MCP adapter for Jentic API for AI agent use.\n    tools:\n    - name: registeraccount\n      description: Jentic Register a new account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n \
  \     call: jentic.registeraccount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchapis\n      description: Jentic Search for APIs and workflows\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jentic.searchapis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadexecutioninfo\n      description: Jentic Load execution information for operations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jentic.loadexecutioninfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executeoperation\n      description: Jentic Execute an API operation or workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jentic.executeoperation\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n\
  \    JENTIC_TOKEN: JENTIC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jentic/refs/heads/main/capabilities/jentic-capability.yaml
tags:
- Jentic
- API
tools:
- description: Jentic Register a new account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registeraccount
- description: Jentic Search for APIs and workflows
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchapis
- description: Jentic Load execution information for operations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: loadexecutioninfo
- description: Jentic Execute an API operation or workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executeoperation
---
