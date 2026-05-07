---
categories: []
consumed_apis: []
description: The OpsGenie Account API provides endpoints for retrieving account-level information and configuration settings. Developers can use this API to access details about their OpsGenie account, including plan information and account metadata. It serves as a foundational API for administrative operations and account management within the OpsGenie platform.
layout: capability
name: OpsGenie Account API
operations:
- description: Get account info
  method: GET
  name: getaccount
  path: /v2/account
personas: []
provider_name: OpsGenie
provider_slug: opsgenie
search_terms:
- opsgenie
- monitoring
- operations
- get account info
- getaccount
- alerts
- incident management
- on-call
- api
slug: opsgenie-capability
source_filename: opsgenie-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpsGenie Account API\n  description: The OpsGenie Account API provides endpoints for retrieving account-level information and configuration settings.\n    Developers can use this API to access details about their OpsGenie account, including plan information and account metadata.\n    It serves as a foundational API for administrative operations and account management within the OpsGenie platform.\n  tags:\n  - Opsgenie\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: opsgenie\n    baseUri: https://api.opsgenie.com\n    description: OpsGenie Account API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{OPSGENIE_TOKEN}}'\n    resources:\n    - name: v2-account\n      path: /v2/account\n      operations:\n      - name: getaccount\n        method: GET\n        description: Get account info\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: opsgenie-rest\n    description: REST adapter for OpsGenie Account API.\n    resources:\n    - path: /v2/account\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Get account info\n        call: opsgenie.getaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: opsgenie-mcp\n    transport: http\n    description: MCP adapter for OpsGenie Account API for AI agent use.\n    tools:\n    - name: getaccount\n      description: Get account info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opsgenie.getaccount\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPSGENIE_TOKEN: OPSGENIE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/opsgenie/refs/heads/main/capabilities/opsgenie-capability.yaml
tags:
- Opsgenie
- API
tools:
- description: Get account info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
---
