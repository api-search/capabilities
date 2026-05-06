---
categories: []
consumed_apis: []
description: Bank of America provides developer APIs for banking services including payments, account management, and treasury services. The APIs enable corporate clients and fintech partners to integrate banking operations.
layout: capability
name: Bank of America API
operations:
- description: Get API status
  method: GET
  name: getstatus
  path: /status
personas: []
provider_name: Bank of America
provider_slug: bank-of-america
search_terms:
- executive responsible for corporate cash and liquidity management
- corporate banking
- get api status
- analyst managing day-to-day treasury operations and reporting
- payment initiation and tracking across 350+ payment types
- bank
- finance
- ERP Integration
- Corporate Treasurer
- treasury
- getstatus
- cashpro
- corporate cash management, balance reporting, and liquidity
- api
- of
- payments
- Treasury Analyst
- system integration connecting erp/tms to bank of america cashpro apis
- corporate treasury operations including account management, payments, and reporting
- banking
- america
slug: bank-of-america-capability
source_filename: bank-of-america-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bank of America API\n  description: Bank of America provides developer APIs for banking services including payments, account management, and treasury\n    services. The APIs enable corporate clients and fintech partners to integrate banking operations.\n  tags:\n  - Bank\n  - Of\n  - America\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bank-of-america\n    baseUri: https://api.bankofamerica.com\n    description: Bank of America API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BANK_OF_AMERICA_TOKEN}}'\n    resources:\n    - name: status\n      path: /status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get API status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bank-of-america-rest\n\
  \    description: REST adapter for Bank of America API.\n    resources:\n    - path: /status\n      name: getstatus\n      operations:\n      - method: GET\n        name: getstatus\n        description: Get API status\n        call: bank-of-america.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bank-of-america-mcp\n    transport: http\n    description: MCP adapter for Bank of America API for AI agent use.\n    tools:\n    - name: getstatus\n      description: Get API status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bank-of-america.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BANK_OF_AMERICA_TOKEN: BANK_OF_AMERICA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bank-of-america/refs/heads/main/capabilities/bank-of-america-capability.yaml
tags:
- Bank
- Of
- America
- API
tools:
- description: Get API status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
---
