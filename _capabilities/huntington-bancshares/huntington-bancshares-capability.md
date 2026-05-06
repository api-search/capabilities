---
categories: []
consumed_apis: []
description: The Huntington Bank Treasury Management API is part of Huntington's Treasury Management Connectivity Ecosystem, an API-first platform that enables businesses to unify banking, ERP, and financial tools. Built on Apigee X, the platform supports over 500 interfaces and processes more than 10 million transaction events daily, providing real-time visibility into treasury operations, automated payment processing, and seamless integration with enterprise systems.
layout: capability
name: Huntington Bank Treasury Management API
operations:
- description: Get treasury accounts
  method: GET
  name: getaccounts
  path: /accounts
- description: Get account balances
  method: GET
  name: getaccountbalances
  path: /accounts/{accountId}/balances
- description: Get account transactions
  method: GET
  name: gettransactions
  path: /accounts/{accountId}/transactions
- description: Initiate a payment
  method: POST
  name: initiatepayment
  path: /payments
personas: []
provider_name: Huntington Bancshares
provider_slug: huntington-bancshares
search_terms:
- getaccountbalances
- get account transactions
- initiate a payment
- open banking
- getaccounts
- erp integration
- api
- huntington
- initiatepayment
- gettransactions
- get treasury accounts
- banking
- treasury
- bancshares
- get account balances
- payments
slug: huntington-bancshares-capability
source_filename: huntington-bancshares-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Huntington Bank Treasury Management API\n  description: The Huntington Bank Treasury Management API is part of Huntington's Treasury Management Connectivity Ecosystem,\n    an API-first platform that enables businesses to unify banking, ERP, and financial tools. Built on Apigee X, the platform\n    supports over 500 interfaces and processes more than 10 million transaction events daily, providing real-time visibility\n    into treasury operations, automated payment processing, and seamless integration with enterprise systems.\n  tags:\n  - Huntington\n  - Bancshares\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: huntington-bancshares\n    baseUri: https://api.huntington.com/v1\n    description: Huntington Bank Treasury Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HUNTINGTON_BANCSHARES_TOKEN}}'\n    resources:\n    - name: accounts\n\
  \      path: /accounts\n      operations:\n      - name: getaccounts\n        method: GET\n        description: Get treasury accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-balances\n      path: /accounts/{accountId}/balances\n      operations:\n      - name: getaccountbalances\n        method: GET\n        description: Get account balances\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-transactions\n      path: /accounts/{accountId}/transactions\n      operations:\n      - name: gettransactions\n        method: GET\n        description: Get account transactions\n        inputParameters:\n\
  \        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The unique account identifier\n        - name: fromDate\n          in: query\n          type: string\n        - name: toDate\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments\n      path: /payments\n      operations:\n      - name: initiatepayment\n        method: POST\n        description: Initiate a payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: huntington-bancshares-rest\n    description: REST adapter for Huntington Bank Treasury Management API.\n    resources:\n    - path: /accounts\n      name: getaccounts\n      operations:\n      - method: GET\n        name: getaccounts\n \
  \       description: Get treasury accounts\n        call: huntington-bancshares.getaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/balances\n      name: getaccountbalances\n      operations:\n      - method: GET\n        name: getaccountbalances\n        description: Get account balances\n        call: huntington-bancshares.getaccountbalances\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/transactions\n      name: gettransactions\n      operations:\n      - method: GET\n        name: gettransactions\n        description: Get account transactions\n        call: huntington-bancshares.gettransactions\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payments\n      name: initiatepayment\n      operations:\n      - method:\
  \ POST\n        name: initiatepayment\n        description: Initiate a payment\n        call: huntington-bancshares.initiatepayment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: huntington-bancshares-mcp\n    transport: http\n    description: MCP adapter for Huntington Bank Treasury Management API for AI agent use.\n    tools:\n    - name: getaccounts\n      description: Get treasury accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: huntington-bancshares.getaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountbalances\n      description: Get account balances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: huntington-bancshares.getaccountbalances\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n   \
  \     type: string\n        description: The unique account identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettransactions\n      description: Get account transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: huntington-bancshares.gettransactions\n      with:\n        accountId: tools.accountId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      inputParameters:\n      - name: accountId\n        type: string\n        description: The unique account identifier\n        required: true\n      - name: fromDate\n        type: string\n        description: fromDate\n      - name: toDate\n        type: string\n        description: toDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiatepayment\n      description: Initiate a payment\n      hints:\n        readOnly: false\n        destructive: false\n     \
  \   idempotent: false\n      call: huntington-bancshares.initiatepayment\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HUNTINGTON_BANCSHARES_TOKEN: HUNTINGTON_BANCSHARES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/huntington-bancshares/refs/heads/main/capabilities/huntington-bancshares-capability.yaml
tags:
- Huntington
- Bancshares
- API
tools:
- description: Get treasury accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccounts
- description: Get account balances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountbalances
- description: Get account transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransactions
- description: Initiate a payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiatepayment
---
