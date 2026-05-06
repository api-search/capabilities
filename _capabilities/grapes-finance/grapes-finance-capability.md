---
categories: []
consumed_apis: []
description: Grapes is an embedded stablecoin onramp and offramp solution that enables businesses and developers to integrate fiat-to-stablecoin and stablecoin-to-fiat transactions. Supports buying and selling stablecoins such as USDC and QCAD with CAD and USD across Ethereum, Algorand, and Stellar networks.
layout: capability
name: Grapes Finance API
operations:
- description: List users
  method: GET
  name: get-users
  path: /users
- description: Create user
  method: POST
  name: post-users
  path: /users
- description: Get user
  method: GET
  name: get-users-userid
  path: /users/{userId}
- description: Submit KYC application
  method: POST
  name: post-kyc
  path: /kyc
- description: List wallets
  method: GET
  name: get-wallets
  path: /wallets
- description: Create wallet
  method: POST
  name: post-wallets
  path: /wallets
- description: List orders
  method: GET
  name: get-orders
  path: /orders
- description: Create order
  method: POST
  name: post-orders
  path: /orders
- description: List contacts
  method: GET
  name: get-contacts
  path: /contacts
- description: Create contact
  method: POST
  name: post-contacts
  path: /contacts
- description: List organizations
  method: GET
  name: get-organizations
  path: /organizations
- description: Create organization
  method: POST
  name: post-organizations
  path: /organizations
personas: []
provider_name: Grapes Finance
provider_slug: grapes-finance
search_terms:
- get users
- get users userid
- create contact
- list organizations
- post wallets
- embedded finance
- post organizations
- finance
- create user
- list wallets
- create organization
- get contacts
- create wallet
- api
- post users
- grapes
- fiat
- get wallets
- post contacts
- create order
- get user
- list orders
- payments
- list users
- cryptocurrency
- get organizations
- offramp
- list contacts
- submit kyc application
- get orders
- onramp
- stablecoin
- post kyc
- post orders
slug: grapes-finance-capability
source_filename: grapes-finance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Grapes Finance API\n  description: Grapes is an embedded stablecoin onramp and offramp solution that enables businesses and developers to integrate\n    fiat-to-stablecoin and stablecoin-to-fiat transactions. Supports buying and selling stablecoins such as USDC and QCAD\n    with CAD and USD across Ethereum, Algorand, and Stellar networks.\n  tags:\n  - Grapes\n  - Finance\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: grapes-finance\n    baseUri: https://api.demo.grapesfinance.com\n    description: Grapes Finance API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{GRAPES_FINANCE_TOKEN}}'\n    resources:\n    - name: users\n      path: /users\n      operations:\n      - name: get-users\n        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: post-users\n        method: POST\n        description: Create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid\n      path: /users/{userId}\n      operations:\n      - name: get-users-userid\n        method: GET\n        description: Get user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kyc\n      path: /kyc\n      operations:\n      - name: post-kyc\n        method: POST\n        description: Submit KYC application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wallets\n      path: /wallets\n      operations:\n\
  \      - name: get-wallets\n        method: GET\n        description: List wallets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-wallets\n        method: POST\n        description: Create wallet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      operations:\n      - name: get-orders\n        method: GET\n        description: List orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-orders\n        method: POST\n        description: Create order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /contacts\n      operations:\n      - name: get-contacts\n    \
  \    method: GET\n        description: List contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-contacts\n        method: POST\n        description: Create contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /organizations\n      operations:\n      - name: get-organizations\n        method: GET\n        description: List organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-organizations\n        method: POST\n        description: Create organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: grapes-finance-rest\n  \
  \  description: REST adapter for Grapes Finance API.\n    resources:\n    - path: /users\n      name: get-users\n      operations:\n      - method: GET\n        name: get-users\n        description: List users\n        call: grapes-finance.get-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: post-users\n      operations:\n      - method: POST\n        name: post-users\n        description: Create user\n        call: grapes-finance.post-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}\n      name: get-users-userid\n      operations:\n      - method: GET\n        name: get-users-userid\n        description: Get user\n        call: grapes-finance.get-users-userid\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kyc\n      name: post-kyc\n      operations:\n      - method: POST\n    \
  \    name: post-kyc\n        description: Submit KYC application\n        call: grapes-finance.post-kyc\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wallets\n      name: get-wallets\n      operations:\n      - method: GET\n        name: get-wallets\n        description: List wallets\n        call: grapes-finance.get-wallets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wallets\n      name: post-wallets\n      operations:\n      - method: POST\n        name: post-wallets\n        description: Create wallet\n        call: grapes-finance.post-wallets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders\n      name: get-orders\n      operations:\n      - method: GET\n        name: get-orders\n        description: List orders\n        call: grapes-finance.get-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders\n    \
  \  name: post-orders\n      operations:\n      - method: POST\n        name: post-orders\n        description: Create order\n        call: grapes-finance.post-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: get-contacts\n      operations:\n      - method: GET\n        name: get-contacts\n        description: List contacts\n        call: grapes-finance.get-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /contacts\n      name: post-contacts\n      operations:\n      - method: POST\n        name: post-contacts\n        description: Create contact\n        call: grapes-finance.post-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations\n      name: get-organizations\n      operations:\n      - method: GET\n        name: get-organizations\n        description: List organizations\n        call: grapes-finance.get-organizations\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations\n      name: post-organizations\n      operations:\n      - method: POST\n        name: post-organizations\n        description: Create organization\n        call: grapes-finance.post-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: grapes-finance-mcp\n    transport: http\n    description: MCP adapter for Grapes Finance API for AI agent use.\n    tools:\n    - name: get-users\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-finance.get-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-users\n      description: Create user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grapes-finance.post-users\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-users-userid\n      description: Get user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-finance.get-users-userid\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-kyc\n      description: Submit KYC application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grapes-finance.post-kyc\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-wallets\n      description: List wallets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-finance.get-wallets\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: post-wallets\n      description: Create wallet\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grapes-finance.post-wallets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-orders\n      description: List orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-finance.get-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-orders\n      description: Create order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grapes-finance.post-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contacts\n      description: List contacts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-finance.get-contacts\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: post-contacts\n      description: Create contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grapes-finance.post-contacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-organizations\n      description: List organizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grapes-finance.get-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-organizations\n      description: Create organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grapes-finance.post-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GRAPES_FINANCE_TOKEN: GRAPES_FINANCE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/grapes-finance/refs/heads/main/capabilities/grapes-finance-capability.yaml
tags:
- Grapes
- Finance
- API
tools:
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-users
- description: Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-users
- description: Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-users-userid
- description: Submit KYC application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-kyc
- description: List wallets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-wallets
- description: Create wallet
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-wallets
- description: List orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-orders
- description: Create order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-orders
- description: List contacts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-contacts
- description: Create contact
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-contacts
- description: List organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-organizations
- description: Create organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-organizations
---
