---
categories: []
consumed_apis: []
description: The Global Payments Unified Payments API is a cloud-powered REST API providing partners and developers with a single integration point for payment facilitation, card issuing, and multi-currency payment processing. Supports sandbox testing, comprehensive SDKs, and OAuth 2.0 authentication.
layout: capability
name: Global Payments Unified Payments API
operations:
- description: List transactions
  method: GET
  name: listtransactions
  path: /transactions
- description: Create a transaction
  method: POST
  name: createtransaction
  path: /transactions
- description: List payment methods
  method: GET
  name: listpaymentmethods
  path: /payment-methods
- description: Store a payment method
  method: POST
  name: createpaymentmethod
  path: /payment-methods
- description: List settlements
  method: GET
  name: listsettlements
  path: /settlements
- description: List disputes
  method: GET
  name: listdisputes
  path: /disputes
personas: []
provider_name: Global Payments
provider_slug: global-payments
search_terms:
- listdisputes
- global
- createpaymentmethod
- api
- ecommerce
- create a transaction
- list disputes
- store a payment method
- listpaymentmethods
- listtransactions
- payment processing
- payment technology
- list payment methods
- list settlements
- createtransaction
- listsettlements
- pos
- payments
- list transactions
slug: global-payments-capability
source_filename: global-payments-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Global Payments Unified Payments API\n  description: The Global Payments Unified Payments API is a cloud-powered REST API providing partners and developers with\n    a single integration point for payment facilitation, card issuing, and multi-currency payment processing. Supports sandbox\n    testing, comprehensive SDKs, and OAuth 2.0 authentication.\n  tags:\n  - Global\n  - Payments\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: global-payments\n    baseUri: https://apis.globalpay.com\n    description: Global Payments Unified Payments API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GLOBAL_PAYMENTS_TOKEN}}'\n    resources:\n    - name: transactions\n      path: /transactions\n      operations:\n      - name: listtransactions\n        method: GET\n        description: List transactions\n        inputParameters:\n        - name: startDate\n  \
  \        in: query\n          type: string\n          description: Filter transactions from this date.\n        - name: endDate\n          in: query\n          type: string\n          description: Filter transactions up to this date.\n        - name: status\n          in: query\n          type: string\n          description: Filter by transaction status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtransaction\n        method: POST\n        description: Create a transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-methods\n      path: /payment-methods\n      operations:\n      - name: listpaymentmethods\n        method: GET\n        description: List payment methods\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: createpaymentmethod\n        method: POST\n        description: Store a payment method\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: settlements\n      path: /settlements\n      operations:\n      - name: listsettlements\n        method: GET\n        description: List settlements\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          description: Filter settlements from this date.\n        - name: endDate\n          in: query\n          type: string\n          description: Filter settlements up to this date.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: disputes\n      path: /disputes\n      operations:\n      - name: listdisputes\n        method: GET\n        description: List disputes\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: global-payments-rest\n    description: REST adapter for Global Payments Unified Payments API.\n    resources:\n    - path: /transactions\n      name: listtransactions\n      operations:\n      - method: GET\n        name: listtransactions\n        description: List transactions\n        call: global-payments.listtransactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transactions\n      name: createtransaction\n      operations:\n      - method: POST\n        name: createtransaction\n        description: Create a transaction\n        call: global-payments.createtransaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payment-methods\n      name: listpaymentmethods\n      operations:\n      - method: GET\n        name: listpaymentmethods\n       \
  \ description: List payment methods\n        call: global-payments.listpaymentmethods\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payment-methods\n      name: createpaymentmethod\n      operations:\n      - method: POST\n        name: createpaymentmethod\n        description: Store a payment method\n        call: global-payments.createpaymentmethod\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /settlements\n      name: listsettlements\n      operations:\n      - method: GET\n        name: listsettlements\n        description: List settlements\n        call: global-payments.listsettlements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /disputes\n      name: listdisputes\n      operations:\n      - method: GET\n        name: listdisputes\n        description: List disputes\n        call: global-payments.listdisputes\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: global-payments-mcp\n    transport: http\n    description: MCP adapter for Global Payments Unified Payments API for AI agent use.\n    tools:\n    - name: listtransactions\n      description: List transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: global-payments.listtransactions\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n        status: tools.status\n      inputParameters:\n      - name: startDate\n        type: string\n        description: Filter transactions from this date.\n      - name: endDate\n        type: string\n        description: Filter transactions up to this date.\n      - name: status\n        type: string\n        description: Filter by transaction status.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtransaction\n      description: Create a transaction\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: global-payments.createtransaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpaymentmethods\n      description: List payment methods\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: global-payments.listpaymentmethods\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpaymentmethod\n      description: Store a payment method\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: global-payments.createpaymentmethod\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsettlements\n      description: List settlements\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: global-payments.listsettlements\n      with:\n     \
  \   startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: startDate\n        type: string\n        description: Filter settlements from this date.\n      - name: endDate\n        type: string\n        description: Filter settlements up to this date.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdisputes\n      description: List disputes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: global-payments.listdisputes\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GLOBAL_PAYMENTS_TOKEN: GLOBAL_PAYMENTS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/global-payments/refs/heads/main/capabilities/global-payments-capability.yaml
tags:
- Global
- Payments
- API
tools:
- description: List transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransactions
- description: Create a transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtransaction
- description: List payment methods
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpaymentmethods
- description: Store a payment method
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpaymentmethod
- description: List settlements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsettlements
- description: List disputes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdisputes
---
