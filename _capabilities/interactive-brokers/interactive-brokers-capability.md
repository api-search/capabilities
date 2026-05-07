---
categories: []
consumed_apis: []
description: The Interactive Brokers Web API is a RESTful API that provides programmatic access to IBKR trading, portfolio management, market data, and account information. The API consolidates the Client Portal Web API, Digital Account Management, and Flex Web Service into a unified interface. It supports OAuth 2.0 authentication and provides endpoints for order placement, portfolio monitoring, real-time and historical market data, and account management across global markets.
layout: capability
name: Interactive Brokers Web API
operations:
- description: Get authentication status
  method: POST
  name: getauthstatus
  path: /iserver/auth/status
- description: Get brokerage accounts
  method: GET
  name: getaccounts
  path: /iserver/accounts
- description: Place an order
  method: POST
  name: placeorder
  path: /iserver/account/{accountId}/orders
- description: Get live orders
  method: GET
  name: getliveorders
  path: /iserver/account/orders
- description: Get portfolio positions
  method: GET
  name: getpositions
  path: /portfolio/{accountId}/positions/{pageId}
- description: Get account summary
  method: GET
  name: getaccountsummary
  path: /portfolio/{accountId}/summary
- description: Get market data snapshot
  method: GET
  name: getmarketdatasnapshot
  path: /iserver/marketdata/snapshot
- description: Get historical market data
  method: GET
  name: getmarketdatahistory
  path: /iserver/marketdata/history
- description: Search contracts
  method: POST
  name: searchcontracts
  path: /iserver/secdef/search
personas: []
provider_name: Interactive Brokers
provider_slug: interactive-brokers
search_terms:
- get portfolio positions
- getpositions
- get historical market data
- get authentication status
- get account summary
- get market data snapshot
- api
- orders
- brokers
- searchcontracts
- get brokerage accounts
- brokerage
- getaccountsummary
- interactive
- trading
- portfolio
- getauthstatus
- placeorder
- getmarketdatahistory
- get live orders
- search contracts
- getaccounts
- getmarketdatasnapshot
- market data
- place an order
- getliveorders
slug: interactive-brokers-capability
source_filename: interactive-brokers-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Interactive Brokers Web API\n  description: The Interactive Brokers Web API is a RESTful API that provides programmatic access to IBKR trading, portfolio\n    management, market data, and account information. The API consolidates the Client Portal Web API, Digital Account Management,\n    and Flex Web Service into a unified interface. It supports OAuth 2.0 authentication and provides endpoints for order placement,\n    portfolio monitoring, real-time and historical market data, and account management across global markets.\n  tags:\n  - Interactive\n  - Brokers\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: interactive-brokers\n    baseUri: https://localhost:5000/v1/api\n    description: Interactive Brokers Web API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{INTERACTIVE_BROKERS_TOKEN}}'\n    resources:\n    - name: iserver-auth-status\n     \
  \ path: /iserver/auth/status\n      operations:\n      - name: getauthstatus\n        method: POST\n        description: Get authentication status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: iserver-accounts\n      path: /iserver/accounts\n      operations:\n      - name: getaccounts\n        method: GET\n        description: Get brokerage accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: iserver-account-accountid-orders\n      path: /iserver/account/{accountId}/orders\n      operations:\n      - name: placeorder\n        method: POST\n        description: Place an order\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The account identifier\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: iserver-account-orders\n      path: /iserver/account/orders\n      operations:\n      - name: getliveorders\n        method: GET\n        description: Get live orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolio-accountid-positions-pageid\n      path: /portfolio/{accountId}/positions/{pageId}\n      operations:\n      - name: getpositions\n        method: GET\n        description: Get portfolio positions\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The account identifier\n        - name: pageId\n          in: path\n          type: string\n          required: true\n          description: Page number for pagination (starts at 0)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: portfolio-accountid-summary\n      path: /portfolio/{accountId}/summary\n      operations:\n      - name: getaccountsummary\n        method: GET\n        description: Get account summary\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: iserver-marketdata-snapshot\n      path: /iserver/marketdata/snapshot\n      operations:\n      - name: getmarketdatasnapshot\n        method: GET\n        description: Get market data snapshot\n        inputParameters:\n        - name: conids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of contract IDs\n        - name: fields\n          in: query\n          type: string\n\
  \          description: Comma-separated list of field IDs to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: iserver-marketdata-history\n      path: /iserver/marketdata/history\n      operations:\n      - name: getmarketdatahistory\n        method: GET\n        description: Get historical market data\n        inputParameters:\n        - name: conid\n          in: query\n          type: string\n          required: true\n          description: Contract identifier\n        - name: period\n          in: query\n          type: string\n          required: true\n          description: Time period (e.g., 1d, 1w, 1m, 1y)\n        - name: bar\n          in: query\n          type: string\n          required: true\n          description: Bar size (e.g., 1min, 5min, 1h, 1d)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: iserver-secdef-search\n      path: /iserver/secdef/search\n      operations:\n      - name: searchcontracts\n        method: POST\n        description: Search contracts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: interactive-brokers-rest\n    description: REST adapter for Interactive Brokers Web API.\n    resources:\n    - path: /iserver/auth/status\n      name: getauthstatus\n      operations:\n      - method: POST\n        name: getauthstatus\n        description: Get authentication status\n        call: interactive-brokers.getauthstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /iserver/accounts\n      name: getaccounts\n      operations:\n      - method: GET\n        name: getaccounts\n        description: Get brokerage accounts\n        call: interactive-brokers.getaccounts\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /iserver/account/{accountId}/orders\n      name: placeorder\n      operations:\n      - method: POST\n        name: placeorder\n        description: Place an order\n        call: interactive-brokers.placeorder\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /iserver/account/orders\n      name: getliveorders\n      operations:\n      - method: GET\n        name: getliveorders\n        description: Get live orders\n        call: interactive-brokers.getliveorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /portfolio/{accountId}/positions/{pageId}\n      name: getpositions\n      operations:\n      - method: GET\n        name: getpositions\n        description: Get portfolio positions\n        call: interactive-brokers.getpositions\n        with:\n          accountId: rest.accountId\n\
  \          pageId: rest.pageId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /portfolio/{accountId}/summary\n      name: getaccountsummary\n      operations:\n      - method: GET\n        name: getaccountsummary\n        description: Get account summary\n        call: interactive-brokers.getaccountsummary\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /iserver/marketdata/snapshot\n      name: getmarketdatasnapshot\n      operations:\n      - method: GET\n        name: getmarketdatasnapshot\n        description: Get market data snapshot\n        call: interactive-brokers.getmarketdatasnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /iserver/marketdata/history\n      name: getmarketdatahistory\n      operations:\n      - method: GET\n        name: getmarketdatahistory\n        description: Get historical market\
  \ data\n        call: interactive-brokers.getmarketdatahistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /iserver/secdef/search\n      name: searchcontracts\n      operations:\n      - method: POST\n        name: searchcontracts\n        description: Search contracts\n        call: interactive-brokers.searchcontracts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: interactive-brokers-mcp\n    transport: http\n    description: MCP adapter for Interactive Brokers Web API for AI agent use.\n    tools:\n    - name: getauthstatus\n      description: Get authentication status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: interactive-brokers.getauthstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccounts\n      description: Get brokerage accounts\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: interactive-brokers.getaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: placeorder\n      description: Place an order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: interactive-brokers.placeorder\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: The account identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getliveorders\n      description: Get live orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interactive-brokers.getliveorders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpositions\n      description: Get portfolio positions\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: interactive-brokers.getpositions\n      with:\n        accountId: tools.accountId\n        pageId: tools.pageId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: The account identifier\n        required: true\n      - name: pageId\n        type: string\n        description: Page number for pagination (starts at 0)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountsummary\n      description: Get account summary\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interactive-brokers.getaccountsummary\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: The account identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n  \
  \  - name: getmarketdatasnapshot\n      description: Get market data snapshot\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interactive-brokers.getmarketdatasnapshot\n      with:\n        conids: tools.conids\n        fields: tools.fields\n      inputParameters:\n      - name: conids\n        type: string\n        description: Comma-separated list of contract IDs\n        required: true\n      - name: fields\n        type: string\n        description: Comma-separated list of field IDs to return\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmarketdatahistory\n      description: Get historical market data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: interactive-brokers.getmarketdatahistory\n      with:\n        conid: tools.conid\n        period: tools.period\n        bar: tools.bar\n      inputParameters:\n      - name: conid\n    \
  \    type: string\n        description: Contract identifier\n        required: true\n      - name: period\n        type: string\n        description: Time period (e.g., 1d, 1w, 1m, 1y)\n        required: true\n      - name: bar\n        type: string\n        description: Bar size (e.g., 1min, 5min, 1h, 1d)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcontracts\n      description: Search contracts\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: interactive-brokers.searchcontracts\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    INTERACTIVE_BROKERS_TOKEN: INTERACTIVE_BROKERS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/interactive-brokers/refs/heads/main/capabilities/interactive-brokers-capability.yaml
tags:
- Interactive
- Brokers
- API
tools:
- description: Get authentication status
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getauthstatus
- description: Get brokerage accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccounts
- description: Place an order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: placeorder
- description: Get live orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getliveorders
- description: Get portfolio positions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpositions
- description: Get account summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountsummary
- description: Get market data snapshot
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmarketdatasnapshot
- description: Get historical market data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmarketdatahistory
- description: Search contracts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchcontracts
---
