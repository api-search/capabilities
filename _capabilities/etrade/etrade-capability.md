---
categories: []
consumed_apis: []
description: The E*TRADE Developer Platform exposes REST APIs for account management, quote retrieval, options chains, order placement, and market data. Access is granted to E*TRADE customers via OAuth 1.0a after registering as a developer at https://developer.etrade.com/home.
layout: capability
name: E*TRADE API
operations:
- description: List accounts
  method: GET
  name: listaccounts
  path: /accounts/list
- description: Get account balance
  method: GET
  name: getaccountbalance
  path: /accounts/{accountIdKey}/balance
- description: View portfolio
  method: GET
  name: viewportfolio
  path: /accounts/{accountIdKey}/portfolio
- description: List transactions
  method: GET
  name: listtransactions
  path: /accounts/{accountIdKey}/transactions
- description: Get quotes
  method: GET
  name: getquotes
  path: /market/quote/{symbols}
- description: Look up option chains
  method: GET
  name: getoptionchains
  path: /market/optionchains
- description: Preview order
  method: POST
  name: previeworder
  path: /accounts/{accountIdKey}/orders/preview
- description: Place order
  method: POST
  name: placeorder
  path: /accounts/{accountIdKey}/orders/place
personas: []
provider_name: Etrade
provider_slug: etrade
search_terms:
- previeworder
- stocks
- getaccountbalance
- viewportfolio
- getquotes
- futures
- api
- view portfolio
- list accounts
- options
- brokerage
- get account balance
- etrade
- bonds
- listtransactions
- trading
- getoptionchains
- placeorder
- look up option chains
- financial
- listaccounts
- place order
- get quotes
- preview order
- list transactions
slug: etrade-capability
source_filename: etrade-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: E*TRADE API\n  description: The E*TRADE Developer Platform exposes REST APIs for account management, quote retrieval, options chains, order\n    placement, and market data. Access is granted to E*TRADE customers via OAuth 1.0a after registering as a developer at\n    https://developer.etrade.com/home.\n  tags:\n  - Etrade\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: etrade\n    baseUri: https://api.etrade.com/v1\n    description: E*TRADE API HTTP API.\n    resources:\n    - name: accounts-list\n      path: /accounts/list\n      operations:\n      - name: listaccounts\n        method: GET\n        description: List accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountidkey-balance\n      path: /accounts/{accountIdKey}/balance\n      operations:\n      - name:\
  \ getaccountbalance\n        method: GET\n        description: Get account balance\n        inputParameters:\n        - name: accountIdKey\n          in: path\n          type: string\n          required: true\n        - name: instType\n          in: query\n          type: string\n          required: true\n        - name: realTimeNAV\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountidkey-portfolio\n      path: /accounts/{accountIdKey}/portfolio\n      operations:\n      - name: viewportfolio\n        method: GET\n        description: View portfolio\n        inputParameters:\n        - name: accountIdKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountidkey-transactions\n\
  \      path: /accounts/{accountIdKey}/transactions\n      operations:\n      - name: listtransactions\n        method: GET\n        description: List transactions\n        inputParameters:\n        - name: accountIdKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: market-quote-symbols\n      path: /market/quote/{symbols}\n      operations:\n      - name: getquotes\n        method: GET\n        description: Get quotes\n        inputParameters:\n        - name: symbols\n          in: path\n          type: string\n          required: true\n        - name: detailFlag\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: market-optionchains\n      path: /market/optionchains\n      operations:\n      -\
  \ name: getoptionchains\n        method: GET\n        description: Look up option chains\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n        - name: expiryYear\n          in: query\n          type: integer\n        - name: expiryMonth\n          in: query\n          type: integer\n        - name: expiryDay\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountidkey-orders-preview\n      path: /accounts/{accountIdKey}/orders/preview\n      operations:\n      - name: previeworder\n        method: POST\n        description: Preview order\n        inputParameters:\n        - name: accountIdKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: accounts-accountidkey-orders-place\n      path: /accounts/{accountIdKey}/orders/place\n      operations:\n      - name: placeorder\n        method: POST\n        description: Place order\n        inputParameters:\n        - name: accountIdKey\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: etrade-rest\n    description: REST adapter for E*TRADE API.\n    resources:\n    - path: /accounts/list\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: List accounts\n        call: etrade.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountIdKey}/balance\n      name: getaccountbalance\n      operations:\n      - method: GET\n    \
  \    name: getaccountbalance\n        description: Get account balance\n        call: etrade.getaccountbalance\n        with:\n          accountIdKey: rest.accountIdKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountIdKey}/portfolio\n      name: viewportfolio\n      operations:\n      - method: GET\n        name: viewportfolio\n        description: View portfolio\n        call: etrade.viewportfolio\n        with:\n          accountIdKey: rest.accountIdKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountIdKey}/transactions\n      name: listtransactions\n      operations:\n      - method: GET\n        name: listtransactions\n        description: List transactions\n        call: etrade.listtransactions\n        with:\n          accountIdKey: rest.accountIdKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /market/quote/{symbols}\n     \
  \ name: getquotes\n      operations:\n      - method: GET\n        name: getquotes\n        description: Get quotes\n        call: etrade.getquotes\n        with:\n          symbols: rest.symbols\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /market/optionchains\n      name: getoptionchains\n      operations:\n      - method: GET\n        name: getoptionchains\n        description: Look up option chains\n        call: etrade.getoptionchains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountIdKey}/orders/preview\n      name: previeworder\n      operations:\n      - method: POST\n        name: previeworder\n        description: Preview order\n        call: etrade.previeworder\n        with:\n          accountIdKey: rest.accountIdKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountIdKey}/orders/place\n      name: placeorder\n      operations:\n\
  \      - method: POST\n        name: placeorder\n        description: Place order\n        call: etrade.placeorder\n        with:\n          accountIdKey: rest.accountIdKey\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: etrade-mcp\n    transport: http\n    description: MCP adapter for E*TRADE API for AI agent use.\n    tools:\n    - name: listaccounts\n      description: List accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: etrade.listaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountbalance\n      description: Get account balance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: etrade.getaccountbalance\n      with:\n        accountIdKey: tools.accountIdKey\n        instType: tools.instType\n        realTimeNAV: tools.realTimeNAV\n      inputParameters:\n\
  \      - name: accountIdKey\n        type: string\n        description: accountIdKey\n        required: true\n      - name: instType\n        type: string\n        description: instType\n        required: true\n      - name: realTimeNAV\n        type: boolean\n        description: realTimeNAV\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: viewportfolio\n      description: View portfolio\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: etrade.viewportfolio\n      with:\n        accountIdKey: tools.accountIdKey\n      inputParameters:\n      - name: accountIdKey\n        type: string\n        description: accountIdKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtransactions\n      description: List transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: etrade.listtransactions\n\
  \      with:\n        accountIdKey: tools.accountIdKey\n      inputParameters:\n      - name: accountIdKey\n        type: string\n        description: accountIdKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getquotes\n      description: Get quotes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: etrade.getquotes\n      with:\n        symbols: tools.symbols\n        detailFlag: tools.detailFlag\n      inputParameters:\n      - name: symbols\n        type: string\n        description: symbols\n        required: true\n      - name: detailFlag\n        type: string\n        description: detailFlag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoptionchains\n      description: Look up option chains\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: etrade.getoptionchains\n      with:\n\
  \        symbol: tools.symbol\n        expiryYear: tools.expiryYear\n        expiryMonth: tools.expiryMonth\n        expiryDay: tools.expiryDay\n      inputParameters:\n      - name: symbol\n        type: string\n        description: symbol\n        required: true\n      - name: expiryYear\n        type: integer\n        description: expiryYear\n      - name: expiryMonth\n        type: integer\n        description: expiryMonth\n      - name: expiryDay\n        type: integer\n        description: expiryDay\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: previeworder\n      description: Preview order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etrade.previeworder\n      with:\n        accountIdKey: tools.accountIdKey\n      inputParameters:\n      - name: accountIdKey\n        type: string\n        description: accountIdKey\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: placeorder\n      description: Place order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: etrade.placeorder\n      with:\n        accountIdKey: tools.accountIdKey\n      inputParameters:\n      - name: accountIdKey\n        type: string\n        description: accountIdKey\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/etrade/refs/heads/main/capabilities/etrade-capability.yaml
tags:
- Etrade
- API
tools:
- description: List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Get account balance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountbalance
- description: View portfolio
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: viewportfolio
- description: List transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransactions
- description: Get quotes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquotes
- description: Look up option chains
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoptionchains
- description: Preview order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: previeworder
- description: Place order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: placeorder
---
