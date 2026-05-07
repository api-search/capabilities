---
categories: []
consumed_apis: []
description: The MessageBird Balance API provides developers with access to their account balance information. It returns the current payment type, available amount, and currency for the account associated with the API key. This API is useful for monitoring credit usage, building billing dashboards, and setting up automated alerts when account balances fall below a threshold.
layout: capability
name: MessageBird Balance API
operations:
- description: Get account balance
  method: GET
  name: getbalance
  path: /balance
personas: []
provider_name: messagebird
provider_slug: messagebird
search_terms:
- getbalance
- messagebird
- get account balance
- api
slug: messagebird-capability
source_filename: messagebird-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: MessageBird Balance API\n  description: The MessageBird Balance API provides developers with access to their account balance information. It returns\n    the current payment type, available amount, and currency for the account associated with the API key. This API is useful\n    for monitoring credit usage, building billing dashboards, and setting up automated alerts when account balances fall below\n    a threshold.\n  tags:\n  - Messagebird\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: messagebird\n    baseUri: https://rest.messagebird.com\n    description: MessageBird Balance API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{MESSAGEBIRD_TOKEN}}'\n    resources:\n    - name: balance\n      path: /balance\n      operations:\n      - name: getbalance\n        method: GET\n        description: Get account\
  \ balance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: messagebird-rest\n    description: REST adapter for MessageBird Balance API.\n    resources:\n    - path: /balance\n      name: getbalance\n      operations:\n      - method: GET\n        name: getbalance\n        description: Get account balance\n        call: messagebird.getbalance\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: messagebird-mcp\n    transport: http\n    description: MCP adapter for MessageBird Balance API for AI agent use.\n    tools:\n    - name: getbalance\n      description: Get account balance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: messagebird.getbalance\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace:\
  \ env\n  keys:\n    MESSAGEBIRD_TOKEN: MESSAGEBIRD_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/messagebird/refs/heads/main/capabilities/messagebird-capability.yaml
tags:
- Messagebird
- API
tools:
- description: Get account balance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbalance
---
