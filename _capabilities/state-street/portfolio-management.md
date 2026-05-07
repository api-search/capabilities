---
categories: []
consumed_apis: []
description: Workflow capability combining State Street Alpha Data Platform and Fund Connect APIs for institutional investment portfolio management. Enables portfolio managers, analysts, and risk officers to access portfolio positions, transaction history, performance measurement, risk analytics, and ETF order management through a unified interface. Designed for asset managers, pension funds, insurance companies, and endowments using the State Street Alpha platform.
layout: capability
name: State Street Portfolio Management
operations:
- description: List all accessible institutional portfolios
  method: GET
  name: list-portfolios
  path: /v1/portfolios
- description: Get portfolio details
  method: GET
  name: get-portfolio
  path: /v1/portfolios/{portfolioId}
- description: Get current portfolio positions
  method: GET
  name: list-positions
  path: /v1/portfolios/{portfolioId}/positions
- description: Get portfolio transaction history
  method: GET
  name: list-transactions
  path: /v1/portfolios/{portfolioId}/transactions
- description: Get portfolio performance and attribution
  method: GET
  name: get-performance
  path: /v1/portfolios/{portfolioId}/performance
- description: Get portfolio risk analytics
  method: GET
  name: get-risk
  path: /v1/portfolios/{portfolioId}/risk
- description: List ETF funds on Fund Connect
  method: GET
  name: list-etf-funds
  path: /v1/etf/funds
- description: Get ETF portfolio composition basket
  method: GET
  name: get-etf-basket
  path: /v1/etf/funds/{fundId}/baskets
- description: List ETF orders
  method: GET
  name: list-etf-orders
  path: /v1/etf/orders
- description: Submit ETF creation or redemption order
  method: POST
  name: submit-etf-order
  path: /v1/etf/orders
personas: []
provider_name: State Street
provider_slug: state-street
search_terms:
- list current positions in a portfolio as of a given date. returns securities, quantities, market values, cost basis, and unrealized p&l. filter by asset class (equity, fixed_income, cash, derivatives, etc.).
- portfolio performance measurement
- get comprehensive details for a specific state street alpha portfolio including total market value, benchmark, and custodian information.
- portfolio positions and holdings
- list portfolio positions
- portfolio detail
- etf
- get portfolio performance
- etf fund information
- get current portfolio positions
- portfolio transaction history
- list etf orders
- portfolio listing and management
- list all institutional investment portfolios accessible via state street alpha. returns portfolio names, types, base currencies, and current market values.
- list all accessible institutional portfolios
- list transaction history for a portfolio including trades, corporate actions, cash movements, and income events over a specified date range.
- submit etf order
- get performance measurement data for a portfolio including time-weighted returns, benchmark returns, and active returns over a specified period.
- get the current portfolio composition basket for an etf fund showing the in-kind securities and quantities required per creation unit.
- list portfolios
- portfolio risk analytics
- get etf order status
- financial services
- portfolio
- get portfolio
- etf creation and redemption orders
- list etf funds available for creation and redemption on state street fund connect.
- get portfolio transaction history
- list etf funds
- submit an etf creation or redemption order through state street fund connect. specify the fund, order type (creation or redemption), and number of units.
- institutional
- get portfolio performance and attribution
- get portfolio risk analytics
- get the current status of a specific etf creation or redemption order on state street fund connect.
- cancel etf order
- get portfolio details
- list etf funds on fund connect
- get risk analytics for a portfolio including value at risk (var), tracking error, beta, duration, and factor exposures.
- cancel a pending etf creation or redemption order on state street fund connect. only available for orders in pending status.
- get risk
- list portfolio transactions
- risk analytics
- get etf portfolio composition basket
- investment management
- list transactions
- list etf creation and redemption orders submitted through fund connect, filterable by fund, status, and date range.
- get portfolio risk
- get etf basket
- etf portfolio baskets
- submit etf creation or redemption order
- get performance
- list positions
slug: portfolio-management
source_filename: portfolio-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: State Street Portfolio Management\n  description: Workflow capability combining State Street Alpha Data Platform and Fund Connect APIs for institutional investment\n    portfolio management. Enables portfolio managers, analysts, and risk officers to access portfolio positions, transaction\n    history, performance measurement, risk analytics, and ETF order management through a unified interface. Designed for asset\n    managers, pension funds, insurance companies, and endowments using the State Street Alpha platform.\n  tags:\n  - Financial Services\n  - Investment Management\n  - Portfolio\n  - Institutional\n  - ETF\n  - Risk Analytics\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STATE_STREET_CLIENT_ID: STATE_STREET_CLIENT_ID\n    STATE_STREET_CLIENT_SECRET: STATE_STREET_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: state-street-alpha\n    baseUri: https://api.statestreet.com/v1\n\
  \    description: State Street Alpha Data Platform API\n    authentication:\n      type: bearer\n      token: '{{STATE_STREET_ACCESS_TOKEN}}'\n    resources:\n    - name: portfolios\n      path: /portfolios\n      description: Portfolio listing and management\n      operations:\n      - name: list-portfolios\n        method: GET\n        description: List all accessible portfolios\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Portfolios per page\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: portfolioType\n          in: query\n          type: string\n          required: false\n          description: Filter by portfolio type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolio-detail\n\
  \      path: /portfolios/{portfolioId}\n      description: Individual portfolio operations\n      operations:\n      - name: get-portfolio\n        method: GET\n        description: Get portfolio details by ID\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolio-positions\n      path: /portfolios/{portfolioId}/positions\n      description: Portfolio position operations\n      operations:\n      - name: list-portfolio-positions\n        method: GET\n        description: List portfolio positions as of a given date\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        - name: asOfDate\n          in: query\n\
  \          type: string\n          required: false\n          description: As-of date for positions\n        - name: assetClass\n          in: query\n          type: string\n          required: false\n          description: Filter by asset class\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Positions per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolio-transactions\n      path: /portfolios/{portfolioId}/transactions\n      description: Portfolio transaction history\n      operations:\n      - name: list-portfolio-transactions\n        method: GET\n        description: List transactions for a portfolio over a date range\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        - name: startDate\n\
  \          in: query\n          type: string\n          required: true\n          description: Start date\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: End date\n        - name: transactionType\n          in: query\n          type: string\n          required: false\n          description: Filter by transaction type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolio-performance\n      path: /portfolios/{portfolioId}/performance\n      description: Portfolio performance measurement\n      operations:\n      - name: get-portfolio-performance\n        method: GET\n        description: Get performance measurement for a portfolio\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        - name: startDate\n\
  \          in: query\n          type: string\n          required: true\n          description: Measurement start date\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: Measurement end date\n        - name: frequency\n          in: query\n          type: string\n          required: false\n          description: Calculation frequency\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolio-risk\n      path: /portfolios/{portfolioId}/risk\n      description: Portfolio risk analytics\n      operations:\n      - name: get-portfolio-risk\n        method: GET\n        description: Get risk analytics for a portfolio\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        - name: asOfDate\n          in: query\n  \
  \        type: string\n          required: false\n          description: As-of date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: state-street-fund-connect\n    baseUri: https://api.statestreet.com/v1/fund-connect\n    description: State Street Fund Connect ETF Order Management API\n    authentication:\n      type: bearer\n      token: '{{STATE_STREET_ACCESS_TOKEN}}'\n    resources:\n    - name: funds\n      path: /funds\n      description: ETF fund listing\n      operations:\n      - name: list-funds\n        method: GET\n        description: List ETF funds available on Fund Connect\n        inputParameters:\n        - name: market\n          in: query\n          type: string\n          required: false\n          description: Filter by market\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: fund-detail\n      path: /funds/{fundId}\n      description: Individual fund operations\n      operations:\n      - name: get-fund\n        method: GET\n        description: Get ETF fund details\n        inputParameters:\n        - name: fundId\n          in: path\n          type: string\n          required: true\n          description: Fund identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fund-baskets\n      path: /funds/{fundId}/baskets\n      description: ETF portfolio basket\n      operations:\n      - name: get-fund-basket\n        method: GET\n        description: Get ETF portfolio composition basket\n        inputParameters:\n        - name: fundId\n          in: path\n          type: string\n          required: true\n          description: Fund identifier\n        - name: date\n          in: query\n          type: string\n          required: false\n          description:\
  \ Basket date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: ETF order management\n      operations:\n      - name: create-order\n        method: POST\n        description: Submit ETF creation or redemption order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fundId: '{{tools.fundId}}'\n            orderType: '{{tools.orderType}}'\n            units: '{{tools.units}}'\n            settlementType: '{{tools.settlementType}}'\n      - name: list-orders\n        method: GET\n        description: List ETF orders\n        inputParameters:\n        - name: fundId\n          in: query\n          type: string\n          required: false\n          description: Filter by fund\n        - name: status\n          in:\
  \ query\n          type: string\n          required: false\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: order-detail\n      path: /orders/{orderId}\n      description: Individual order operations\n      operations:\n      - name: get-order\n        method: GET\n        description: Get ETF order status and details\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: order-cancel\n      path: /orders/{orderId}/cancel\n      description: Order cancellation\n      operations:\n      - name: cancel-order\n        method: POST\n        description: Cancel a pending ETF order\n        inputParameters:\n        - name:\
  \ orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: state-street-portfolio-management-api\n    description: Unified REST API for State Street institutional portfolio management workflows.\n    resources:\n    - path: /v1/portfolios\n      name: portfolios\n      description: Portfolio listing and management\n      operations:\n      - method: GET\n        name: list-portfolios\n        description: List all accessible institutional portfolios\n        call: state-street-alpha.list-portfolios\n        with:\n          portfolioType: rest.portfolioType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios/{portfolioId}\n      name: portfolio-detail\n      description: Portfolio detail\n  \
  \    operations:\n      - method: GET\n        name: get-portfolio\n        description: Get portfolio details\n        call: state-street-alpha.get-portfolio\n        with:\n          portfolioId: rest.portfolioId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios/{portfolioId}/positions\n      name: positions\n      description: Portfolio positions and holdings\n      operations:\n      - method: GET\n        name: list-positions\n        description: Get current portfolio positions\n        call: state-street-alpha.list-portfolio-positions\n        with:\n          portfolioId: rest.portfolioId\n          asOfDate: rest.asOfDate\n          assetClass: rest.assetClass\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios/{portfolioId}/transactions\n      name: transactions\n      description: Portfolio transaction history\n      operations:\n      - method: GET\n        name: list-transactions\n\
  \        description: Get portfolio transaction history\n        call: state-street-alpha.list-portfolio-transactions\n        with:\n          portfolioId: rest.portfolioId\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios/{portfolioId}/performance\n      name: performance\n      description: Portfolio performance measurement\n      operations:\n      - method: GET\n        name: get-performance\n        description: Get portfolio performance and attribution\n        call: state-street-alpha.get-portfolio-performance\n        with:\n          portfolioId: rest.portfolioId\n          startDate: rest.startDate\n          endDate: rest.endDate\n          frequency: rest.frequency\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios/{portfolioId}/risk\n      name: risk\n      description: Portfolio risk analytics\n     \
  \ operations:\n      - method: GET\n        name: get-risk\n        description: Get portfolio risk analytics\n        call: state-street-alpha.get-portfolio-risk\n        with:\n          portfolioId: rest.portfolioId\n          asOfDate: rest.asOfDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/etf/funds\n      name: etf-funds\n      description: ETF fund information\n      operations:\n      - method: GET\n        name: list-etf-funds\n        description: List ETF funds on Fund Connect\n        call: state-street-fund-connect.list-funds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/etf/funds/{fundId}/baskets\n      name: etf-baskets\n      description: ETF portfolio baskets\n      operations:\n      - method: GET\n        name: get-etf-basket\n        description: Get ETF portfolio composition basket\n        call: state-street-fund-connect.get-fund-basket\n        with:\n          fundId: rest.fundId\n\
  \          date: rest.date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/etf/orders\n      name: etf-orders\n      description: ETF creation and redemption orders\n      operations:\n      - method: GET\n        name: list-etf-orders\n        description: List ETF orders\n        call: state-street-fund-connect.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: submit-etf-order\n        description: Submit ETF creation or redemption order\n        call: state-street-fund-connect.create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: state-street-portfolio-management-mcp\n    transport: http\n    description: MCP server for AI-assisted State Street institutional investment portfolio management.\n    tools:\n    - name: list-portfolios\n      description: List all institutional investment portfolios\
  \ accessible via State Street Alpha. Returns portfolio names,\n        types, base currencies, and current market values.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-street-alpha.list-portfolios\n      with:\n        portfolioType: tools.portfolioType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-portfolio\n      description: Get comprehensive details for a specific State Street Alpha portfolio including total market value, benchmark,\n        and custodian information.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-street-alpha.get-portfolio\n      with:\n        portfolioId: tools.portfolioId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-portfolio-positions\n      description: List current positions in a portfolio as of a given date. Returns securities, quantities, market values,\n        cost basis, and unrealized P&L. Filter by asset\
  \ class (EQUITY, FIXED_INCOME, CASH, DERIVATIVES, etc.).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-street-alpha.list-portfolio-positions\n      with:\n        portfolioId: tools.portfolioId\n        asOfDate: tools.asOfDate\n        assetClass: tools.assetClass\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-portfolio-transactions\n      description: List transaction history for a portfolio including trades, corporate actions, cash movements, and income\n        events over a specified date range.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-street-alpha.list-portfolio-transactions\n      with:\n        portfolioId: tools.portfolioId\n        startDate: tools.startDate\n        endDate: tools.endDate\n        transactionType: tools.transactionType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-portfolio-performance\n      description:\
  \ Get performance measurement data for a portfolio including time-weighted returns, benchmark returns, and\n        active returns over a specified period.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-street-alpha.get-portfolio-performance\n      with:\n        portfolioId: tools.portfolioId\n        startDate: tools.startDate\n        endDate: tools.endDate\n        frequency: tools.frequency\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-portfolio-risk\n      description: Get risk analytics for a portfolio including Value at Risk (VaR), tracking error, beta, duration, and factor\n        exposures.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-street-alpha.get-portfolio-risk\n      with:\n        portfolioId: tools.portfolioId\n        asOfDate: tools.asOfDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-etf-funds\n      description:\
  \ List ETF funds available for creation and redemption on State Street Fund Connect.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-street-fund-connect.list-funds\n      with:\n        market: tools.market\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-etf-basket\n      description: Get the current portfolio composition basket for an ETF fund showing the in-kind securities and quantities\n        required per creation unit.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-street-fund-connect.get-fund-basket\n      with:\n        fundId: tools.fundId\n        date: tools.date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-etf-order\n      description: Submit an ETF creation or redemption order through State Street Fund Connect. Specify the fund, order type\n        (CREATION or REDEMPTION), and number of units.\n      hints:\n        readOnly:\
  \ false\n        openWorld: false\n      call: state-street-fund-connect.create-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-etf-orders\n      description: List ETF creation and redemption orders submitted through Fund Connect, filterable by fund, status, and\n        date range.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-street-fund-connect.list-orders\n      with:\n        fundId: tools.fundId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-etf-order-status\n      description: Get the current status of a specific ETF creation or redemption order on State Street Fund Connect.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-street-fund-connect.get-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-etf-order\n    \
  \  description: Cancel a pending ETF creation or redemption order on State Street Fund Connect. Only available for orders\n        in PENDING status.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: state-street-fund-connect.cancel-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/state-street/refs/heads/main/capabilities/portfolio-management.yaml
tags:
- Financial Services
- Investment Management
- Portfolio
- Institutional
- ETF
- Risk Analytics
tools:
- description: List all institutional investment portfolios accessible via State Street Alpha. Returns portfolio names, types, base currencies, and current market values.
  hints:
    openWorld: false
    readOnly: true
  name: list-portfolios
- description: Get comprehensive details for a specific State Street Alpha portfolio including total market value, benchmark, and custodian information.
  hints:
    openWorld: false
    readOnly: true
  name: get-portfolio
- description: List current positions in a portfolio as of a given date. Returns securities, quantities, market values, cost basis, and unrealized P&L. Filter by asset class (EQUITY, FIXED_INCOME, CASH, DERIVATIVES, etc.).
  hints:
    openWorld: false
    readOnly: true
  name: list-portfolio-positions
- description: List transaction history for a portfolio including trades, corporate actions, cash movements, and income events over a specified date range.
  hints:
    openWorld: false
    readOnly: true
  name: list-portfolio-transactions
- description: Get performance measurement data for a portfolio including time-weighted returns, benchmark returns, and active returns over a specified period.
  hints:
    openWorld: false
    readOnly: true
  name: get-portfolio-performance
- description: Get risk analytics for a portfolio including Value at Risk (VaR), tracking error, beta, duration, and factor exposures.
  hints:
    openWorld: false
    readOnly: true
  name: get-portfolio-risk
- description: List ETF funds available for creation and redemption on State Street Fund Connect.
  hints:
    openWorld: false
    readOnly: true
  name: list-etf-funds
- description: Get the current portfolio composition basket for an ETF fund showing the in-kind securities and quantities required per creation unit.
  hints:
    openWorld: false
    readOnly: true
  name: get-etf-basket
- description: Submit an ETF creation or redemption order through State Street Fund Connect. Specify the fund, order type (CREATION or REDEMPTION), and number of units.
  hints:
    openWorld: false
    readOnly: false
  name: submit-etf-order
- description: List ETF creation and redemption orders submitted through Fund Connect, filterable by fund, status, and date range.
  hints:
    openWorld: false
    readOnly: true
  name: list-etf-orders
- description: Get the current status of a specific ETF creation or redemption order on State Street Fund Connect.
  hints:
    openWorld: false
    readOnly: true
  name: get-etf-order-status
- description: Cancel a pending ETF creation or redemption order on State Street Fund Connect. Only available for orders in PENDING status.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-etf-order
---
