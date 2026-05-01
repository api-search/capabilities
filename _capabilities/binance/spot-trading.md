---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Spot Trading
operations: []
personas: []
provider_name: Binance
provider_slug: binance
search_terms:
- trade on margin with borrowed assets
- cryptocurrency
- finance
- market data
- defi
- api key management, account balances, and commission rates
- developer building algorithmic trading strategies on binance
- real-time and historical price, depth, and trade data
- exchange
- blockchain
- trading
- buy and sell cryptocurrency spot pairs on the binance exchange
- cryptocurrency trader executing spot orders on binance
- deposits, withdrawals, and asset management
- trade usd-m and coin-m perpetual futures contracts
- place and manage spot orders and retrieve market data on binance
slug: spot-trading
source_filename: spot-trading.yaml
source_heading: Capability Spec
source_yaml: "name: Spot Trading\ndescription: >-\n  Workflow capability for executing spot cryptocurrency trades on Binance,\n  including market data retrieval, order placement and management, and\n  account balance monitoring.\nversion: v1\n\nimports:\n  - shared/binance.yaml\n\ntools:\n  - name: get-ticker\n    import: binance.get-ticker\n    description: Get the current price for a cryptocurrency trading pair.\n    inputSchema:\n      type: object\n      required:\n        - symbol\n      properties:\n        symbol:\n          type: string\n          description: Trading pair symbol (e.g. BTCUSDT)\n  - name: get-order-book\n    import: binance.get-order-book\n    description: Get order book depth showing bids and asks for a trading pair.\n    inputSchema:\n      type: object\n      required:\n        - symbol\n      properties:\n        symbol:\n          type: string\n          description: Trading pair symbol\n        limit:\n          type: integer\n          description: Depth limit\
  \ (5, 10, 20, 50, 100, 500, 1000)\n  - name: get-klines\n    import: binance.get-klines\n    description: Get candlestick (OHLCV) chart data for a trading pair.\n    inputSchema:\n      type: object\n      required:\n        - symbol\n        - interval\n      properties:\n        symbol:\n          type: string\n          description: Trading pair symbol\n        interval:\n          type: string\n          description: Candlestick interval (1m, 5m, 15m, 1h, 4h, 1d)\n        limit:\n          type: integer\n          description: Number of candles to return\n  - name: get-account\n    import: binance.get-account\n    description: Get account balances for all assets and trading commissions.\n  - name: create-order\n    import: binance.create-order\n    description: Place a new spot buy or sell order on Binance.\n    inputSchema:\n      type: object\n      required:\n        - symbol\n        - side\n        - type\n        - quantity\n      properties:\n        symbol:\n          type:\
  \ string\n          description: Trading pair symbol (e.g. BTCUSDT)\n        side:\n          type: string\n          description: Order side (BUY or SELL)\n        type:\n          type: string\n          description: Order type (LIMIT, MARKET, STOP_LOSS_LIMIT)\n        quantity:\n          type: number\n          description: Order quantity\n        price:\n          type: number\n          description: Limit price (required for LIMIT orders)\n  - name: get-order\n    import: binance.get-order\n    description: Check the status of an existing order.\n    inputSchema:\n      type: object\n      required:\n        - symbol\n        - orderId\n      properties:\n        symbol:\n          type: string\n          description: Trading pair symbol\n        orderId:\n          type: integer\n          description: Order ID to query\n  - name: cancel-order\n    import: binance.cancel-order\n    description: Cancel an active open order.\n    inputSchema:\n      type: object\n      required:\n\
  \        - symbol\n        - orderId\n      properties:\n        symbol:\n          type: string\n          description: Trading pair symbol\n        orderId:\n          type: integer\n          description: Order ID to cancel\n  - name: list-orders\n    import: binance.list-orders\n    description: List all open orders for a symbol.\n    inputSchema:\n      type: object\n      properties:\n        symbol:\n          type: string\n          description: Trading pair symbol (omit for all symbols)\n  - name: list-trades\n    import: binance.list-trades\n    description: Get trade execution history for a symbol.\n    inputSchema:\n      type: object\n      required:\n        - symbol\n      properties:\n        symbol:\n          type: string\n          description: Trading pair symbol\n        limit:\n          type: integer\n          description: Number of trades to return\n\nexpose:\n  rest:\n    port: 8080\n  mcp:\n    port: 9080\n\npersonas:\n  - id: trader\n    name: Trader\n    description:\
  \ Cryptocurrency trader executing spot orders on Binance\n  - id: quant-developer\n    name: Quant Developer\n    description: Developer building algorithmic trading strategies on Binance\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/binance/refs/heads/main/capabilities/spot-trading.yaml
tags: []
tools: []
---
