---
categories: []
consumed_apis: []
description: The Automation Anywhere API Task Execution API enables developers to invoke API Tasks — a specialized type of cloud-based bot designed to be called synchronously from external applications like a REST service. The API provides endpoints to list API Task allocations, generate unique execution URLs and tokens, and execute API Tasks in real time. API Tasks execute on cloud infrastructure without requiring local Bot Runner devices, and are designed for low latency with near-real-time response rates. The execution URL and authorization token are short-lived and must be refreshed periodically to pre
layout: capability
name: Automation Anywhere API Task Execution API
operations:
- description: List API Task allocations
  method: POST
  name: listapitaskallocations
  path: /config
- description: Generate API Task execution URL and token
  method: POST
  name: generateapitaskaccessdetails
  path: /config/accessdetails
personas: []
provider_name: automation-anywhere
provider_slug: automation-anywhere
search_terms:
- anywhere
- generate api task execution url and token
- listapitaskallocations
- api
- list api task allocations
- generateapitaskaccessdetails
- automation
slug: automation-anywhere-capability
source_filename: automation-anywhere-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Automation Anywhere API Task Execution API\n  description: The Automation Anywhere API Task Execution API enables developers to invoke API Tasks — a specialized type\n    of cloud-based bot designed to be called synchronously from external applications like a REST service. The API provides\n    endpoints to list API Task allocations, generate unique execution URLs and tokens, and execute API Tasks in real time.\n    API Tasks execute on cloud infrastructure without requiring local Bot Runner devices, and are designed for low latency\n    with near-real-time response rates. The execution URL and authorization token are short-lived and must be refreshed periodically\n    to pre\n  tags:\n  - Automation\n  - Anywhere\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: automation-anywhere\n    baseUri: https://your-control-room.automationanywhere.com/orchestrator/v1/hotbot\n\
  \    description: Automation Anywhere API Task Execution API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{AUTOMATION_ANYWHERE_TOKEN}}'\n    resources:\n    - name: config\n      path: /config\n      operations:\n      - name: listapitaskallocations\n        method: POST\n        description: List API Task allocations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: config-accessdetails\n      path: /config/accessdetails\n      operations:\n      - name: generateapitaskaccessdetails\n        method: POST\n        description: Generate API Task execution URL and token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: automation-anywhere-rest\n    description: REST adapter for Automation Anywhere API Task Execution API.\n    resources:\n    -\
  \ path: /config\n      name: listapitaskallocations\n      operations:\n      - method: POST\n        name: listapitaskallocations\n        description: List API Task allocations\n        call: automation-anywhere.listapitaskallocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /config/accessdetails\n      name: generateapitaskaccessdetails\n      operations:\n      - method: POST\n        name: generateapitaskaccessdetails\n        description: Generate API Task execution URL and token\n        call: automation-anywhere.generateapitaskaccessdetails\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: automation-anywhere-mcp\n    transport: http\n    description: MCP adapter for Automation Anywhere API Task Execution API for AI agent use.\n    tools:\n    - name: listapitaskallocations\n      description: List API Task allocations\n      hints:\n        readOnly: false\n   \
  \     destructive: false\n        idempotent: false\n      call: automation-anywhere.listapitaskallocations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateapitaskaccessdetails\n      description: Generate API Task execution URL and token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: automation-anywhere.generateapitaskaccessdetails\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AUTOMATION_ANYWHERE_TOKEN: AUTOMATION_ANYWHERE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/automation-anywhere/refs/heads/main/capabilities/automation-anywhere-capability.yaml
tags:
- Automation
- Anywhere
- API
tools:
- description: List API Task allocations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listapitaskallocations
- description: Generate API Task execution URL and token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateapitaskaccessdetails
---
