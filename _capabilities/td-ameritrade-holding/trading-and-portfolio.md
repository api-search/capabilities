---
categories: []
consumed_apis:
- tdameritrade
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
- investment
- security and instrument search
- market data
- portfolio
- get quotes
- deprecated
- get account
- get detailed account information including balances and current positions
- get all security watchlists for a brokerage account
- get price history
- account transaction history
- security watchlists
- place order
- retrieve orders for the account
- finance
- retrieve account transaction history with optional date range and type filtering
- brokerage account information and balances
- charles schwab
- retrieve all linked td ameritrade brokerage accounts with balances and positions
- td ameritrade
- place a new trade order
- cancel a pending trade order
- search for securities by symbol or description to find trading instruments
- get option chain data for an optionable security symbol
- get watchlists
- get orders
- place a new trade order (market, limit, stop, etc.) for an account
- cancel order
- get historical ohlcv price data for a symbol
- retrieve all linked brokerage accounts with balances and positions
- brokerage
- retrieve account transaction history
- search for securities by symbol or description
- retrieve historical ohlcv price data for a security symbol
- historical price data
- get option chain for an optionable symbol
- trading
- search instruments
- get real-time market quotes for one or more security symbols
- get transactions
- real-time market quotes
- get accounts
- single account details
- get option chain
- get all watchlists for an account
- options chain data
- order management for a brokerage account
- get account balances and positions for a specific account
- get quotes for one or more symbols
- retrieve all orders for a brokerage account with optional status filtering
slug: trading-and-portfolio
source_filename: trading-and-portfolio.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TD Ameritrade Trading and Portfolio Management\"\n  description: >-\n    Workflow capability for automated brokerage trading and portfolio management\n    using the TD Ameritrade API (historical - deprecated May 2024). Enables\n    programmatic trading, account monitoring, market data retrieval, and portfolio\n    analysis. The successor API is the Charles Schwab Trader API.\n  tags:\n    - TD Ameritrade\n    - Finance\n    - Trading\n    - Portfolio\n    - Market Data\n    - Brokerage\n    - Deprecated\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TDAMERITRADE_ACCESS_TOKEN: TDAMERITRADE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: tdameritrade\n      location: ./shared/accounts-trading.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tdameritrade-trading-api\n      description: \"Unified REST API for TD Ameritrade trading and portfolio\
  \ management.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: \"Brokerage account information and balances\"\n          operations:\n            - method: GET\n              name: get-accounts\n              description: \"Retrieve all linked brokerage accounts with balances and positions\"\n              call: \"tdameritrade.get-accounts\"\n              with:\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}\n          name: account-detail\n          description: \"Single account details\"\n          operations:\n            - method: GET\n              name: get-account\n              description: \"Get account balances and positions for a specific account\"\n              call: \"tdameritrade.get-account\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}/orders\n          name: orders\n          description: \"Order management for a brokerage account\"\n          operations:\n            - method: GET\n              name: get-orders\n              description: \"Retrieve orders for the account\"\n              call: \"tdameritrade.get-orders\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: place-order\n              description: \"Place a new trade order\"\n              call: \"tdameritrade.place-order\"\n              with:\n                accountId: \"rest.accountId\"\n                orderType: \"rest.orderType\"\n                session: \"rest.session\"\n                price: \"rest.price\"\n                duration: \"rest.duration\"\n               \
  \ orderStrategyType: \"rest.orderStrategyType\"\n                orderLegCollection: \"rest.orderLegCollection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/quotes\n          name: quotes\n          description: \"Real-time market quotes\"\n          operations:\n            - method: GET\n              name: get-quotes\n              description: \"Get quotes for one or more symbols\"\n              call: \"tdameritrade.get-quotes\"\n              with:\n                symbol: \"rest.symbol\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/price-history/{symbol}\n          name: price-history\n          description: \"Historical price data\"\n          operations:\n            - method: GET\n              name: get-price-history\n              description: \"Get historical OHLCV price data for a symbol\"\n              call: \"tdameritrade.get-price-history\"\
  \n              with:\n                symbol: \"rest.symbol\"\n                periodType: \"rest.periodType\"\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/options\n          name: options\n          description: \"Options chain data\"\n          operations:\n            - method: GET\n              name: get-option-chain\n              description: \"Get option chain for an optionable symbol\"\n              call: \"tdameritrade.get-option-chain\"\n              with:\n                symbol: \"rest.symbol\"\n                contractType: \"rest.contractType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/instruments\n          name: instruments\n          description: \"Security and instrument search\"\n          operations:\n            - method: GET\n              name: search-instruments\n\
  \              description: \"Search for securities by symbol or description\"\n              call: \"tdameritrade.search-instruments\"\n              with:\n                symbol: \"rest.symbol\"\n                projection: \"rest.projection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}/transactions\n          name: transactions\n          description: \"Account transaction history\"\n          operations:\n            - method: GET\n              name: get-transactions\n              description: \"Retrieve account transaction history\"\n              call: \"tdameritrade.get-transactions\"\n              with:\n                accountId: \"rest.accountId\"\n                type: \"rest.type\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \        - path: /v1/accounts/{accountId}/watchlists\n          name: watchlists\n          description: \"Security watchlists\"\n          operations:\n            - method: GET\n              name: get-watchlists\n              description: \"Get all watchlists for an account\"\n              call: \"tdameritrade.get-watchlists\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tdameritrade-trading-mcp\n      transport: http\n      description: \"MCP server for AI-assisted brokerage trading and portfolio management.\"\n      tools:\n        - name: get-accounts\n          description: \"Retrieve all linked TD Ameritrade brokerage accounts with balances and positions\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tdameritrade.get-accounts\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-account\n          description: \"Get detailed account information including balances and current positions\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tdameritrade.get-account\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-orders\n          description: \"Retrieve all orders for a brokerage account with optional status filtering\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tdameritrade.get-orders\"\n          with:\n            accountId: \"tools.accountId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: place-order\n          description: \"Place a new trade order (market, limit,\
  \ stop, etc.) for an account\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tdameritrade.place-order\"\n          with:\n            accountId: \"tools.accountId\"\n            orderType: \"tools.orderType\"\n            session: \"tools.session\"\n            price: \"tools.price\"\n            duration: \"tools.duration\"\n            orderStrategyType: \"tools.orderStrategyType\"\n            orderLegCollection: \"tools.orderLegCollection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-order\n          description: \"Cancel a pending trade order\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tdameritrade.cancel-order\"\n          with:\n            accountId: \"tools.accountId\"\n            orderId: \"tools.orderId\"\n          outputParameters:\n    \
  \        - type: object\n              mapping: \"$.\"\n\n        - name: get-quotes\n          description: \"Get real-time market quotes for one or more security symbols\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tdameritrade.get-quotes\"\n          with:\n            symbol: \"tools.symbol\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-price-history\n          description: \"Retrieve historical OHLCV price data for a security symbol\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tdameritrade.get-price-history\"\n          with:\n            symbol: \"tools.symbol\"\n            periodType: \"tools.periodType\"\n            period: \"tools.period\"\n            frequencyType: \"tools.frequencyType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-option-chain\n\
  \          description: \"Get option chain data for an optionable security symbol\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tdameritrade.get-option-chain\"\n          with:\n            symbol: \"tools.symbol\"\n            contractType: \"tools.contractType\"\n            strategy: \"tools.strategy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-instruments\n          description: \"Search for securities by symbol or description to find trading instruments\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tdameritrade.search-instruments\"\n          with:\n            symbol: \"tools.symbol\"\n            projection: \"tools.projection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-transactions\n          description: \"Retrieve account transaction history\
  \ with optional date range and type filtering\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tdameritrade.get-transactions\"\n          with:\n            accountId: \"tools.accountId\"\n            type: \"tools.type\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-watchlists\n          description: \"Get all security watchlists for a brokerage account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tdameritrade.get-watchlists\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
