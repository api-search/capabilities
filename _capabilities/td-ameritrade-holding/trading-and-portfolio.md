---
categories: []
consumed_apis: []
description: Workflow capability for automated brokerage trading and portfolio management using the TD Ameritrade API (historical - deprecated May 2024). Enables programmatic trading, account monitoring, market data retrieval, and portfolio analysis. The successor API is the Charles Schwab Trader API.
layout: capability
name: TD Ameritrade Trading and Portfolio Management
operations:
- description: Retrieve all linked brokerage accounts with balances and positions
  method: GET
  name: get-accounts
  path: /v1/accounts
- description: Get account balances and positions for a specific account
  method: GET
  name: get-account
  path: /v1/accounts/{accountId}
- description: Retrieve orders for the account
  method: GET
  name: get-orders
  path: /v1/accounts/{accountId}/orders
- description: Place a new trade order
  method: POST
  name: place-order
  path: /v1/accounts/{accountId}/orders
- description: Get quotes for one or more symbols
  method: GET
  name: get-quotes
  path: /v1/quotes
- description: Get historical OHLCV price data for a symbol
  method: GET
  name: get-price-history
  path: /v1/price-history/{symbol}
- description: Get option chain for an optionable symbol
  method: GET
  name: get-option-chain
  path: /v1/options
- description: Search for securities by symbol or description
  method: GET
  name: search-instruments
  path: /v1/instruments
- description: Retrieve account transaction history
  method: GET
  name: get-transactions
  path: /v1/accounts/{accountId}/transactions
- description: Get all watchlists for an account
  method: GET
  name: get-watchlists
  path: /v1/accounts/{accountId}/watchlists
personas: []
provider_name: TD Ameritrade Holding
provider_slug: td-ameritrade-holding
search_terms:
- get account
- get orders
- retrieve account transaction history with optional date range and type filtering
- get option chain
- retrieve all orders for a brokerage account with optional status filtering
- options chain data
- security watchlists
- get option chain data for an optionable security symbol
- charles schwab
- get all watchlists for an account
- get option chain for an optionable symbol
- search for securities by symbol or description to find trading instruments
- brokerage account information and balances
- td ameritrade
- retrieve orders for the account
- get accounts
- deprecated
- get account balances and positions for a specific account
- historical price data
- brokerage
- retrieve all linked brokerage accounts with balances and positions
- search instruments
- order management for a brokerage account
- get watchlists
- retrieve account transaction history
- finance
- place a new trade order (market, limit, stop, etc.) for an account
- get detailed account information including balances and current positions
- get price history
- real-time market quotes
- get quotes for one or more symbols
- account transaction history
- investment
- trading
- cancel order
- portfolio
- retrieve historical ohlcv price data for a security symbol
- security and instrument search
- cancel a pending trade order
- retrieve all linked td ameritrade brokerage accounts with balances and positions
- place a new trade order
- market data
- place order
- get quotes
- get transactions
- get real-time market quotes for one or more security symbols
- get all security watchlists for a brokerage account
- single account details
- get historical ohlcv price data for a symbol
- search for securities by symbol or description
slug: trading-and-portfolio
source_filename: trading-and-portfolio.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TD Ameritrade Trading and Portfolio Management\n  description: Workflow capability for automated brokerage trading and portfolio management using the TD Ameritrade API (historical\n    - deprecated May 2024). Enables programmatic trading, account monitoring, market data retrieval, and portfolio analysis.\n    The successor API is the Charles Schwab Trader API.\n  tags:\n  - TD Ameritrade\n  - Finance\n  - Trading\n  - Portfolio\n  - Market Data\n  - Brokerage\n  - Deprecated\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TDAMERITRADE_ACCESS_TOKEN: TDAMERITRADE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tdameritrade\n    baseUri: https://api.tdameritrade.com/v1\n    description: TD Ameritrade API (deprecated)\n    authentication:\n      type: bearer\n      token: '{{TDAMERITRADE_ACCESS_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      description:\
  \ Account information and balances\n      operations:\n      - name: get-accounts\n        method: GET\n        description: Retrieve all linked brokerage accounts\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Optional fields to include (positions, orders)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Get account balances and positions for a specific account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        - name: fields\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: orders\n      path: /accounts/{accountId}/orders\n      description: Order management\n      operations:\n      - name: get-orders\n        method: GET\n        description: Get orders for a specific account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: place-order\n        method: POST\n        description: Place a new order for a specific account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            orderType: '{{tools.orderType}}'\n\
  \            session: '{{tools.session}}'\n            price: '{{tools.price}}'\n            duration: '{{tools.duration}}'\n            orderStrategyType: '{{tools.orderStrategyType}}'\n            orderLegCollection: '{{tools.orderLegCollection}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-order\n        method: DELETE\n        description: Cancel a specific order\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: market-data\n      path: /marketdata\n      description: Market quotes and price history\n      operations:\n      - name: get-quote\n        method: GET\n        description:\
  \ Get real-time quote for a single symbol\n        inputParameters:\n        - name: symbol\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-quotes\n        method: GET\n        description: Get quotes for multiple symbols\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of symbols\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-price-history\n        method: GET\n        description: Get historical price data for a symbol\n        inputParameters:\n        - name: symbol\n          in: path\n          type: string\n          required: true\n        - name: periodType\n          in: query\n          type: string\n\
  \          required: false\n        - name: period\n          in: query\n          type: integer\n          required: false\n        - name: frequencyType\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-option-chain\n        method: GET\n        description: Get option chain for an optionable symbol\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n        - name: contractType\n          in: query\n          type: string\n          required: false\n        - name: strategy\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instruments\n      path: /instruments\n      description: Security and\
  \ instrument search\n      operations:\n      - name: search-instruments\n        method: GET\n        description: Search for instruments by symbol or description\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n        - name: projection\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: watchlists\n      path: /accounts/{accountId}/watchlists\n      description: Watchlist management\n      operations:\n      - name: get-watchlists\n        method: GET\n        description: Get all watchlists for an account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: transactions\n      path: /accounts/{accountId}/transactions\n      description: Account transaction history\n      operations:\n      - name: get-transactions\n        method: GET\n        description: Get transaction history for an account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: type\n          in: query\n          type: string\n          required: false\n        - name: startDate\n          in: query\n          type: string\n          required: false\n        - name: endDate\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tdameritrade-trading-api\n    description: Unified REST API for TD Ameritrade trading and portfolio management.\n    resources:\n    - path: /v1/accounts\n\
  \      name: accounts\n      description: Brokerage account information and balances\n      operations:\n      - method: GET\n        name: get-accounts\n        description: Retrieve all linked brokerage accounts with balances and positions\n        call: tdameritrade.get-accounts\n        with:\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}\n      name: account-detail\n      description: Single account details\n      operations:\n      - method: GET\n        name: get-account\n        description: Get account balances and positions for a specific account\n        call: tdameritrade.get-account\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/orders\n      name: orders\n      description: Order management for a brokerage account\n      operations:\n      - method: GET\n       \
  \ name: get-orders\n        description: Retrieve orders for the account\n        call: tdameritrade.get-orders\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: place-order\n        description: Place a new trade order\n        call: tdameritrade.place-order\n        with:\n          accountId: rest.accountId\n          orderType: rest.orderType\n          session: rest.session\n          price: rest.price\n          duration: rest.duration\n          orderStrategyType: rest.orderStrategyType\n          orderLegCollection: rest.orderLegCollection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quotes\n      name: quotes\n      description: Real-time market quotes\n      operations:\n      - method: GET\n        name: get-quotes\n        description: Get quotes for one or more symbols\n        call: tdameritrade.get-quotes\n       \
  \ with:\n          symbol: rest.symbol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/price-history/{symbol}\n      name: price-history\n      description: Historical price data\n      operations:\n      - method: GET\n        name: get-price-history\n        description: Get historical OHLCV price data for a symbol\n        call: tdameritrade.get-price-history\n        with:\n          symbol: rest.symbol\n          periodType: rest.periodType\n          period: rest.period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/options\n      name: options\n      description: Options chain data\n      operations:\n      - method: GET\n        name: get-option-chain\n        description: Get option chain for an optionable symbol\n        call: tdameritrade.get-option-chain\n        with:\n          symbol: rest.symbol\n          contractType: rest.contractType\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/instruments\n      name: instruments\n      description: Security and instrument search\n      operations:\n      - method: GET\n        name: search-instruments\n        description: Search for securities by symbol or description\n        call: tdameritrade.search-instruments\n        with:\n          symbol: rest.symbol\n          projection: rest.projection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/transactions\n      name: transactions\n      description: Account transaction history\n      operations:\n      - method: GET\n        name: get-transactions\n        description: Retrieve account transaction history\n        call: tdameritrade.get-transactions\n        with:\n          accountId: rest.accountId\n          type: rest.type\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/accounts/{accountId}/watchlists\n      name: watchlists\n      description: Security watchlists\n      operations:\n      - method: GET\n        name: get-watchlists\n        description: Get all watchlists for an account\n        call: tdameritrade.get-watchlists\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tdameritrade-trading-mcp\n    transport: http\n    description: MCP server for AI-assisted brokerage trading and portfolio management.\n    tools:\n    - name: get-accounts\n      description: Retrieve all linked TD Ameritrade brokerage accounts with balances and positions\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tdameritrade.get-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Get detailed account information including balances and\
  \ current positions\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tdameritrade.get-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-orders\n      description: Retrieve all orders for a brokerage account with optional status filtering\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tdameritrade.get-orders\n      with:\n        accountId: tools.accountId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: place-order\n      description: Place a new trade order (market, limit, stop, etc.) for an account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tdameritrade.place-order\n      with:\n        accountId: tools.accountId\n        orderType: tools.orderType\n        session: tools.session\n        price: tools.price\n   \
  \     duration: tools.duration\n        orderStrategyType: tools.orderStrategyType\n        orderLegCollection: tools.orderLegCollection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-order\n      description: Cancel a pending trade order\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tdameritrade.cancel-order\n      with:\n        accountId: tools.accountId\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-quotes\n      description: Get real-time market quotes for one or more security symbols\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tdameritrade.get-quotes\n      with:\n        symbol: tools.symbol\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-price-history\n      description: Retrieve historical OHLCV price data for a security symbol\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: tdameritrade.get-price-history\n      with:\n        symbol: tools.symbol\n        periodType: tools.periodType\n        period: tools.period\n        frequencyType: tools.frequencyType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-option-chain\n      description: Get option chain data for an optionable security symbol\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tdameritrade.get-option-chain\n      with:\n        symbol: tools.symbol\n        contractType: tools.contractType\n        strategy: tools.strategy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-instruments\n      description: Search for securities by symbol or description to find trading instruments\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tdameritrade.search-instruments\n      with:\n        symbol: tools.symbol\n     \
  \   projection: tools.projection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-transactions\n      description: Retrieve account transaction history with optional date range and type filtering\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tdameritrade.get-transactions\n      with:\n        accountId: tools.accountId\n        type: tools.type\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-watchlists\n      description: Get all security watchlists for a brokerage account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tdameritrade.get-watchlists\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/td-ameritrade-holding/refs/heads/main/capabilities/trading-and-portfolio.yaml
tags:
- TD Ameritrade
- Finance
- Trading
- Portfolio
- Market Data
- Brokerage
- Deprecated
tools:
- description: Retrieve all linked TD Ameritrade brokerage accounts with balances and positions
  hints:
    openWorld: false
    readOnly: true
  name: get-accounts
- description: Get detailed account information including balances and current positions
  hints:
    openWorld: false
    readOnly: true
  name: get-account
- description: Retrieve all orders for a brokerage account with optional status filtering
  hints:
    openWorld: false
    readOnly: true
  name: get-orders
- description: Place a new trade order (market, limit, stop, etc.) for an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: place-order
- description: Cancel a pending trade order
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-order
- description: Get real-time market quotes for one or more security symbols
  hints:
    openWorld: true
    readOnly: true
  name: get-quotes
- description: Retrieve historical OHLCV price data for a security symbol
  hints:
    openWorld: true
    readOnly: true
  name: get-price-history
- description: Get option chain data for an optionable security symbol
  hints:
    openWorld: true
    readOnly: true
  name: get-option-chain
- description: Search for securities by symbol or description to find trading instruments
  hints:
    openWorld: true
    readOnly: true
  name: search-instruments
- description: Retrieve account transaction history with optional date range and type filtering
  hints:
    openWorld: false
    readOnly: true
  name: get-transactions
- description: Get all security watchlists for a brokerage account
  hints:
    openWorld: false
    readOnly: true
  name: get-watchlists
---
