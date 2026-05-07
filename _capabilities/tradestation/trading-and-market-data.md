---
categories: []
consumed_apis: []
description: Unified trading and market data workflow combining account management, order execution, real-time quotes, historical bar data, and options analysis. Used by algorithmic traders and application developers to build complete trading applications covering market data access and order lifecycle management.
layout: capability
name: TradeStation Trading and Market Data
operations:
- description: Retrieve all brokerage accounts
  method: GET
  name: get-accounts
  path: /v1/accounts
- description: Retrieve current account balances
  method: GET
  name: get-balances
  path: /v1/accounts/{accountIds}/balances
- description: Retrieve open positions
  method: GET
  name: get-positions
  path: /v1/accounts/{accountIds}/positions
- description: Retrieve active orders
  method: GET
  name: get-orders
  path: /v1/accounts/{accountIds}/orders
- description: Retrieve real-time quote snapshots
  method: GET
  name: get-quotes
  path: /v1/quotes/{symbols}
- description: Retrieve OHLC bar chart history
  method: GET
  name: get-bars
  path: /v1/bars/{symbol}
- description: Retrieve symbol information
  method: GET
  name: get-symbols
  path: /v1/symbols/{symbols}
- description: Retrieve option expiration dates
  method: GET
  name: get-option-expirations
  path: /v1/options/{underlying}/expirations
- description: Retrieve option strike prices
  method: GET
  name: get-option-strikes
  path: /v1/options/{underlying}/strikes
- description: Place a new order
  method: POST
  name: place-order
  path: /v1/orders
- description: Modify an existing order
  method: PUT
  name: replace-order
  path: /v1/orders/{orderId}
- description: Cancel an existing order
  method: DELETE
  name: cancel-order
  path: /v1/orders/{orderId}
- description: Preview order costs before placing
  method: POST
  name: confirm-order
  path: /v1/order-confirm
- description: Place a group order
  method: POST
  name: place-order-group
  path: /v1/group-orders
- description: Retrieve cryptocurrency trading pairs
  method: GET
  name: get-crypto-pairs
  path: /v1/crypto-pairs
personas: []
provider_name: TradeStation
provider_slug: tradestation
search_terms:
- get bars
- cancel an existing open tradestation order
- get orders
- stocks
- replace order
- retrieve cryptocurrency trading pairs
- cryptocurrency
- retrieve cryptocurrency wallet balances for a tradestation account
- preview order costs before placing
- get wallets
- manage existing orders
- get crypto pairs
- retrieve real-time bid, ask, last price, and volume for symbols
- retrieve real-time quote snapshots
- futures
- option expiration dates
- cancel an existing order
- active account orders
- group order placement (bracket, oco, oso)
- place a new stock, option, futures, or crypto order on tradestation
- account positions
- options
- account balance information
- retrieve ohlc bar chart history
- retrieve open positions
- modify an existing order
- place a group order
- get accounts
- retrieve symbol metadata including exchange, category, and contract specifications
- brokerage
- historical bar chart data
- retrieve current account balances
- option strike prices
- retrieve open positions including market value, unrealized p/l, and asset type
- finance
- retrieve current cash, equity, buying power, and margin balances for accounts
- retrieve active orders
- get symbols
- real-time market quotes
- cryptocurrency trading pairs
- get option strikes
- trading
- order placement and management
- cancel order
- confirm order
- retrieve available strike prices for options on an underlying symbol
- retrieve available cryptocurrency trading pairs on tradestation
- accounts
- brokerage account information
- order execution
- get positions
- retrieve tradestation brokerage accounts and account metadata
- place a new order
- retrieve historical filled, cancelled, and rejected orders
- retrieve active orders for one or more tradestation accounts
- calculate the risk/reward profile for an option strategy
- retrieve all brokerage accounts
- retrieve option expiration dates
- place a bracket, oco, or oso group order on tradestation
- market data
- get quotes
- symbol details and metadata
- place order
- retrieve available option expiration dates for an underlying symbol
- retrieve historical ohlc bar chart data for a symbol
- get historical orders
- retrieve symbol information
- retrieve option strike prices
- calculate option risk reward
- get option expirations
- preview estimated commissions, costs, and margin requirements before placing an order
- place order group
- order cost preview
- get balances
slug: trading-and-market-data
source_filename: trading-and-market-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TradeStation Trading and Market Data\n  description: Unified trading and market data workflow combining account management, order execution, real-time quotes, historical\n    bar data, and options analysis. Used by algorithmic traders and application developers to build complete trading applications\n    covering market data access and order lifecycle management.\n  tags:\n  - Accounts\n  - Brokerage\n  - Cryptocurrency\n  - Finance\n  - Market Data\n  - Options\n  - Order Execution\n  - Trading\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRADESTATION_ACCESS_TOKEN: TRADESTATION_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tradestation-api\n    baseUri: https://api.tradestation.com\n    description: TradeStation REST API for brokerage and market data\n    authentication:\n      type: bearer\n      token: '{{TRADESTATION_ACCESS_TOKEN}}'\n    resources:\n    - name:\
  \ accounts\n      path: /v3/brokerage/accounts\n      description: Brokerage account management\n      operations:\n      - name: get-accounts\n        method: GET\n        description: Retrieve all brokerage accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-balances\n        method: GET\n        description: Retrieve account balances\n        inputParameters:\n        - name: accountIds\n          in: path\n          type: string\n          required: true\n          description: Comma-separated account identifiers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-balances-bod\n        method: GET\n        description: Retrieve beginning-of-day account balances\n        inputParameters:\n        - name: accountIds\n          in: path\n          type: string\n          required: true\n   \
  \       description: Comma-separated account identifiers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-positions\n        method: GET\n        description: Retrieve account positions\n        inputParameters:\n        - name: accountIds\n          in: path\n          type: string\n          required: true\n          description: Comma-separated account identifiers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-orders\n        method: GET\n        description: Retrieve active account orders\n        inputParameters:\n        - name: accountIds\n          in: path\n          type: string\n          required: true\n          description: Comma-separated account identifiers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: get-historical-orders\n        method: GET\n        description: Retrieve historical orders\n        inputParameters:\n        - name: accountIds\n          in: path\n          type: string\n          required: true\n          description: Comma-separated account identifiers\n        - name: since\n          in: query\n          type: string\n          required: false\n          description: Filter since date (MM-DD-YYYY)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of orders per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-wallets\n        method: GET\n        description: Retrieve cryptocurrency wallets\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: market-data\n      path: /v3/marketdata\n      description: Real-time and historical market data\n      operations:\n      - name: get-quotes\n        method: GET\n        description: Retrieve real-time quote snapshots\n        inputParameters:\n        - name: symbols\n          in: path\n          type: string\n          required: true\n          description: Comma-separated symbol identifiers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-bars\n        method: GET\n        description: Retrieve historical bar chart data (OHLC)\n        inputParameters:\n        - name: symbol\n          in: path\n          type: string\n          required: true\n          description: Symbol to retrieve bars for\n        - name: interval\n          in: query\n          type: integer\n  \
  \        required: false\n          description: Bar interval\n        - name: unit\n          in: query\n          type: string\n          required: false\n          description: Time unit (Minute, Daily, Weekly, Monthly)\n        - name: barsBack\n          in: query\n          type: integer\n          required: false\n          description: Number of bars going back\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-symbols\n        method: GET\n        description: Retrieve detailed symbol information\n        inputParameters:\n        - name: symbols\n          in: path\n          type: string\n          required: true\n          description: Comma-separated symbol identifiers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-crypto-pairs\n        method: GET\n        description: Retrieve cryptocurrency\
  \ trading pairs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: options\n      path: /v3/marketdata/options\n      description: Options market data\n      operations:\n      - name: get-option-expirations\n        method: GET\n        description: Retrieve option expiration dates\n        inputParameters:\n        - name: underlying\n          in: path\n          type: string\n          required: true\n          description: Underlying symbol\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-option-strikes\n        method: GET\n        description: Retrieve option strike prices\n        inputParameters:\n        - name: underlying\n          in: path\n          type: string\n          required: true\n          description: Underlying symbol\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n      - name: get-option-spread-types\n        method: GET\n        description: Retrieve option spread types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: calculate-option-risk-reward\n        method: POST\n        description: Calculate option risk/reward profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            SpreadPrice: '{{tools.spread_price}}'\n            Legs: '{{tools.legs}}'\n    - name: order-execution\n      path: /v3/orderexecution\n      description: Order placement and management\n      operations:\n      - name: place-order\n        method: POST\n        description: Place a new order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            AccountID: '{{tools.account_id}}'\n            Symbol: '{{tools.symbol}}'\n            Quantity: '{{tools.quantity}}'\n            OrderType: '{{tools.order_type}}'\n            TradeAction: '{{tools.trade_action}}'\n            TimeInForce: '{{tools.time_in_force}}'\n            LimitPrice: '{{tools.limit_price}}'\n      - name: confirm-order\n        method: POST\n        description: Preview order costs before placement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            AccountID: '{{tools.account_id}}'\n            Symbol: '{{tools.symbol}}'\n            Quantity: '{{tools.quantity}}'\n            OrderType: '{{tools.order_type}}'\n            TradeAction: '{{tools.trade_action}}'\n            TimeInForce: '{{tools.time_in_force}}'\n\
  \      - name: replace-order\n        method: PUT\n        description: Modify an existing order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Quantity: '{{tools.quantity}}'\n            LimitPrice: '{{tools.limit_price}}'\n      - name: cancel-order\n        method: DELETE\n        description: Cancel an existing order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: place-order-group\n        method: POST\n        description: Place\
  \ a group order (OCO, bracket, OSO)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Type: '{{tools.group_type}}'\n            Orders: '{{tools.orders}}'\n    - name: reference-data\n      path: /v3/orderexecution\n      description: Order execution reference data\n      operations:\n      - name: get-activation-triggers\n        method: GET\n        description: Retrieve activation trigger methods\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-routes\n        method: GET\n        description: Retrieve order routing destinations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: trading-and-market-data-api\n    description:\
  \ Unified REST API for TradeStation trading and market data workflows.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Brokerage account information\n      operations:\n      - method: GET\n        name: get-accounts\n        description: Retrieve all brokerage accounts\n        call: tradestation-api.get-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountIds}/balances\n      name: balances\n      description: Account balance information\n      operations:\n      - method: GET\n        name: get-balances\n        description: Retrieve current account balances\n        call: tradestation-api.get-balances\n        with:\n          accountIds: rest.accountIds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountIds}/positions\n      name: positions\n      description: Account positions\n      operations:\n      - method: GET\n       \
  \ name: get-positions\n        description: Retrieve open positions\n        call: tradestation-api.get-positions\n        with:\n          accountIds: rest.accountIds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountIds}/orders\n      name: orders\n      description: Active account orders\n      operations:\n      - method: GET\n        name: get-orders\n        description: Retrieve active orders\n        call: tradestation-api.get-orders\n        with:\n          accountIds: rest.accountIds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quotes/{symbols}\n      name: quotes\n      description: Real-time market quotes\n      operations:\n      - method: GET\n        name: get-quotes\n        description: Retrieve real-time quote snapshots\n        call: tradestation-api.get-quotes\n        with:\n          symbols: rest.symbols\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /v1/bars/{symbol}\n      name: bars\n      description: Historical bar chart data\n      operations:\n      - method: GET\n        name: get-bars\n        description: Retrieve OHLC bar chart history\n        call: tradestation-api.get-bars\n        with:\n          symbol: rest.symbol\n          interval: rest.interval\n          unit: rest.unit\n          barsBack: rest.barsBack\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/symbols/{symbols}\n      name: symbols\n      description: Symbol details and metadata\n      operations:\n      - method: GET\n        name: get-symbols\n        description: Retrieve symbol information\n        call: tradestation-api.get-symbols\n        with:\n          symbols: rest.symbols\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/options/{underlying}/expirations\n      name: option-expirations\n      description: Option expiration dates\n\
  \      operations:\n      - method: GET\n        name: get-option-expirations\n        description: Retrieve option expiration dates\n        call: tradestation-api.get-option-expirations\n        with:\n          underlying: rest.underlying\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/options/{underlying}/strikes\n      name: option-strikes\n      description: Option strike prices\n      operations:\n      - method: GET\n        name: get-option-strikes\n        description: Retrieve option strike prices\n        call: tradestation-api.get-option-strikes\n        with:\n          underlying: rest.underlying\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: place-orders\n      description: Order placement and management\n      operations:\n      - method: POST\n        name: place-order\n        description: Place a new order\n        call: tradestation-api.place-order\n        with:\n\
  \          account_id: rest.AccountID\n          symbol: rest.Symbol\n          quantity: rest.Quantity\n          order_type: rest.OrderType\n          trade_action: rest.TradeAction\n          time_in_force: rest.TimeInForce\n          limit_price: rest.LimitPrice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}\n      name: order-management\n      description: Manage existing orders\n      operations:\n      - method: PUT\n        name: replace-order\n        description: Modify an existing order\n        call: tradestation-api.replace-order\n        with:\n          orderId: rest.orderId\n          quantity: rest.Quantity\n          limit_price: rest.LimitPrice\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-order\n        description: Cancel an existing order\n        call: tradestation-api.cancel-order\n        with:\n          orderId: rest.orderId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/order-confirm\n      name: order-confirm\n      description: Order cost preview\n      operations:\n      - method: POST\n        name: confirm-order\n        description: Preview order costs before placing\n        call: tradestation-api.confirm-order\n        with:\n          account_id: rest.AccountID\n          symbol: rest.Symbol\n          quantity: rest.Quantity\n          order_type: rest.OrderType\n          trade_action: rest.TradeAction\n          time_in_force: rest.TimeInForce\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/group-orders\n      name: group-orders\n      description: Group order placement (bracket, OCO, OSO)\n      operations:\n      - method: POST\n        name: place-order-group\n        description: Place a group order\n        call: tradestation-api.place-order-group\n        with:\n          group_type: rest.Type\n      \
  \    orders: rest.Orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/crypto-pairs\n      name: crypto-pairs\n      description: Cryptocurrency trading pairs\n      operations:\n      - method: GET\n        name: get-crypto-pairs\n        description: Retrieve cryptocurrency trading pairs\n        call: tradestation-api.get-crypto-pairs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: trading-and-market-data-mcp\n    transport: http\n    description: MCP server for AI-assisted TradeStation trading and market data operations.\n    tools:\n    - name: get-accounts\n      description: Retrieve TradeStation brokerage accounts and account metadata\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tradestation-api.get-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-balances\n      description: Retrieve current\
  \ cash, equity, buying power, and margin balances for accounts\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tradestation-api.get-balances\n      with:\n        accountIds: tools.account_ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-positions\n      description: Retrieve open positions including market value, unrealized P/L, and asset type\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tradestation-api.get-positions\n      with:\n        accountIds: tools.account_ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-orders\n      description: Retrieve active orders for one or more TradeStation accounts\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tradestation-api.get-orders\n      with:\n        accountIds: tools.account_ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-historical-orders\n\
  \      description: Retrieve historical filled, cancelled, and rejected orders\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tradestation-api.get-historical-orders\n      with:\n        accountIds: tools.account_ids\n        since: tools.since\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-quotes\n      description: Retrieve real-time bid, ask, last price, and volume for symbols\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tradestation-api.get-quotes\n      with:\n        symbols: tools.symbols\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bars\n      description: Retrieve historical OHLC bar chart data for a symbol\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tradestation-api.get-bars\n      with:\n        symbol: tools.symbol\n        interval: tools.interval\n        unit: tools.unit\n        barsBack: tools.bars_back\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-symbols\n      description: Retrieve symbol metadata including exchange, category, and contract specifications\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tradestation-api.get-symbols\n      with:\n        symbols: tools.symbols\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-option-expirations\n      description: Retrieve available option expiration dates for an underlying symbol\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tradestation-api.get-option-expirations\n      with:\n        underlying: tools.underlying\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-option-strikes\n      description: Retrieve available strike prices for options on an underlying symbol\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tradestation-api.get-option-strikes\n\
  \      with:\n        underlying: tools.underlying\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: calculate-option-risk-reward\n      description: Calculate the risk/reward profile for an option strategy\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tradestation-api.calculate-option-risk-reward\n      with:\n        spread_price: tools.spread_price\n        legs: tools.legs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: confirm-order\n      description: Preview estimated commissions, costs, and margin requirements before placing an order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tradestation-api.confirm-order\n      with:\n        account_id: tools.account_id\n        symbol: tools.symbol\n        quantity: tools.quantity\n        order_type: tools.order_type\n        trade_action: tools.trade_action\n        time_in_force: tools.time_in_force\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: place-order\n      description: Place a new stock, option, futures, or crypto order on TradeStation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tradestation-api.place-order\n      with:\n        account_id: tools.account_id\n        symbol: tools.symbol\n        quantity: tools.quantity\n        order_type: tools.order_type\n        trade_action: tools.trade_action\n        time_in_force: tools.time_in_force\n        limit_price: tools.limit_price\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-order\n      description: Cancel an existing open TradeStation order\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tradestation-api.cancel-order\n      with:\n        orderId: tools.order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: place-order-group\n\
  \      description: Place a bracket, OCO, or OSO group order on TradeStation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tradestation-api.place-order-group\n      with:\n        group_type: tools.group_type\n        orders: tools.orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-crypto-pairs\n      description: Retrieve available cryptocurrency trading pairs on TradeStation\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tradestation-api.get-crypto-pairs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-wallets\n      description: Retrieve cryptocurrency wallet balances for a TradeStation account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tradestation-api.get-wallets\n      with:\n        accountId: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tradestation/refs/heads/main/capabilities/trading-and-market-data.yaml
tags:
- Accounts
- Brokerage
- Cryptocurrency
- Finance
- Market Data
- Options
- Order Execution
- Trading
tools:
- description: Retrieve TradeStation brokerage accounts and account metadata
  hints:
    openWorld: false
    readOnly: true
  name: get-accounts
- description: Retrieve current cash, equity, buying power, and margin balances for accounts
  hints:
    openWorld: false
    readOnly: true
  name: get-balances
- description: Retrieve open positions including market value, unrealized P/L, and asset type
  hints:
    openWorld: false
    readOnly: true
  name: get-positions
- description: Retrieve active orders for one or more TradeStation accounts
  hints:
    openWorld: false
    readOnly: true
  name: get-orders
- description: Retrieve historical filled, cancelled, and rejected orders
  hints:
    openWorld: false
    readOnly: true
  name: get-historical-orders
- description: Retrieve real-time bid, ask, last price, and volume for symbols
  hints:
    openWorld: true
    readOnly: true
  name: get-quotes
- description: Retrieve historical OHLC bar chart data for a symbol
  hints:
    openWorld: true
    readOnly: true
  name: get-bars
- description: Retrieve symbol metadata including exchange, category, and contract specifications
  hints:
    openWorld: true
    readOnly: true
  name: get-symbols
- description: Retrieve available option expiration dates for an underlying symbol
  hints:
    openWorld: true
    readOnly: true
  name: get-option-expirations
- description: Retrieve available strike prices for options on an underlying symbol
  hints:
    openWorld: true
    readOnly: true
  name: get-option-strikes
- description: Calculate the risk/reward profile for an option strategy
  hints:
    openWorld: false
    readOnly: true
  name: calculate-option-risk-reward
- description: Preview estimated commissions, costs, and margin requirements before placing an order
  hints:
    openWorld: false
    readOnly: true
  name: confirm-order
- description: Place a new stock, option, futures, or crypto order on TradeStation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: place-order
- description: Cancel an existing open TradeStation order
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-order
- description: Place a bracket, OCO, or OSO group order on TradeStation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: place-order-group
- description: Retrieve available cryptocurrency trading pairs on TradeStation
  hints:
    openWorld: true
    readOnly: true
  name: get-crypto-pairs
- description: Retrieve cryptocurrency wallet balances for a TradeStation account
  hints:
    openWorld: false
    readOnly: true
  name: get-wallets
---
