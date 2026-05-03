---
categories: []
consumed_apis:
- state-street-alpha
- state-street-fund-connect
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
- list etf funds
- institutional
- cancel a pending etf creation or redemption order on state street fund connect. only available for orders in pending status.
- cancel etf order
- get portfolio
- investment management
- portfolio transaction history
- get portfolio risk
- etf creation and redemption orders
- submit an etf creation or redemption order through state street fund connect. specify the fund, order type (creation or redemption), and number of units.
- list portfolio transactions
- get risk analytics for a portfolio including value at risk (var), tracking error, beta, duration, and factor exposures.
- etf
- list transactions
- financial services
- get portfolio performance and attribution
- list etf funds available for creation and redemption on state street fund connect.
- get the current status of a specific etf creation or redemption order on state street fund connect.
- get etf basket
- list portfolios
- portfolio detail
- get etf portfolio composition basket
- get performance measurement data for a portfolio including time-weighted returns, benchmark returns, and active returns over a specified period.
- get current portfolio positions
- list transaction history for a portfolio including trades, corporate actions, cash movements, and income events over a specified date range.
- list positions
- list all accessible institutional portfolios
- etf portfolio baskets
- list portfolio positions
- portfolio risk analytics
- get the current portfolio composition basket for an etf fund showing the in-kind securities and quantities required per creation unit.
- submit etf creation or redemption order
- get portfolio transaction history
- get comprehensive details for a specific state street alpha portfolio including total market value, benchmark, and custodian information.
- portfolio performance measurement
- submit etf order
- portfolio listing and management
- list current positions in a portfolio as of a given date. returns securities, quantities, market values, cost basis, and unrealized p&l. filter by asset class (equity, fixed_income, cash, derivatives, etc.).
- portfolio positions and holdings
- list etf creation and redemption orders submitted through fund connect, filterable by fund, status, and date range.
- get portfolio risk analytics
- risk analytics
- get portfolio details
- list etf funds on fund connect
- list all institutional investment portfolios accessible via state street alpha. returns portfolio names, types, base currencies, and current market values.
- portfolio
- etf fund information
- list etf orders
- get performance
- get risk
- get portfolio performance
- get etf order status
slug: portfolio-management
source_filename: portfolio-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"State Street Portfolio Management\"\n  description: >-\n    Workflow capability combining State Street Alpha Data Platform and Fund Connect APIs\n    for institutional investment portfolio management. Enables portfolio managers, analysts,\n    and risk officers to access portfolio positions, transaction history, performance\n    measurement, risk analytics, and ETF order management through a unified interface.\n    Designed for asset managers, pension funds, insurance companies, and endowments\n    using the State Street Alpha platform.\n  tags:\n    - Financial Services\n    - Investment Management\n    - Portfolio\n    - Institutional\n    - ETF\n    - Risk Analytics\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STATE_STREET_CLIENT_ID: STATE_STREET_CLIENT_ID\n      STATE_STREET_CLIENT_SECRET: STATE_STREET_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: state-street-alpha\n\
  \      location: ./shared/alpha-data-platform.yaml\n    - import: state-street-fund-connect\n      location: ./shared/fund-connect.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: state-street-portfolio-management-api\n      description: \"Unified REST API for State Street institutional portfolio management workflows.\"\n      resources:\n        - path: /v1/portfolios\n          name: portfolios\n          description: \"Portfolio listing and management\"\n          operations:\n            - method: GET\n              name: list-portfolios\n              description: \"List all accessible institutional portfolios\"\n              call: \"state-street-alpha.list-portfolios\"\n              with:\n                portfolioType: \"rest.portfolioType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}\n          name: portfolio-detail\n          description: \"Portfolio\
  \ detail\"\n          operations:\n            - method: GET\n              name: get-portfolio\n              description: \"Get portfolio details\"\n              call: \"state-street-alpha.get-portfolio\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}/positions\n          name: positions\n          description: \"Portfolio positions and holdings\"\n          operations:\n            - method: GET\n              name: list-positions\n              description: \"Get current portfolio positions\"\n              call: \"state-street-alpha.list-portfolio-positions\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n                asOfDate: \"rest.asOfDate\"\n                assetClass: \"rest.assetClass\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}/transactions\n          name: transactions\n          description: \"Portfolio transaction history\"\n          operations:\n            - method: GET\n              name: list-transactions\n              description: \"Get portfolio transaction history\"\n              call: \"state-street-alpha.list-portfolio-transactions\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}/performance\n          name: performance\n          description: \"Portfolio performance measurement\"\n          operations:\n            - method: GET\n              name: get-performance\n              description: \"Get portfolio performance and attribution\"\n              call: \"state-street-alpha.get-portfolio-performance\"\
  \n              with:\n                portfolioId: \"rest.portfolioId\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                frequency: \"rest.frequency\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}/risk\n          name: risk\n          description: \"Portfolio risk analytics\"\n          operations:\n            - method: GET\n              name: get-risk\n              description: \"Get portfolio risk analytics\"\n              call: \"state-street-alpha.get-portfolio-risk\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n                asOfDate: \"rest.asOfDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/etf/funds\n          name: etf-funds\n          description: \"ETF fund information\"\n          operations:\n       \
  \     - method: GET\n              name: list-etf-funds\n              description: \"List ETF funds on Fund Connect\"\n              call: \"state-street-fund-connect.list-funds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/etf/funds/{fundId}/baskets\n          name: etf-baskets\n          description: \"ETF portfolio baskets\"\n          operations:\n            - method: GET\n              name: get-etf-basket\n              description: \"Get ETF portfolio composition basket\"\n              call: \"state-street-fund-connect.get-fund-basket\"\n              with:\n                fundId: \"rest.fundId\"\n                date: \"rest.date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/etf/orders\n          name: etf-orders\n          description: \"ETF creation and redemption orders\"\n          operations:\n            - method:\
  \ GET\n              name: list-etf-orders\n              description: \"List ETF orders\"\n              call: \"state-street-fund-connect.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-etf-order\n              description: \"Submit ETF creation or redemption order\"\n              call: \"state-street-fund-connect.create-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: state-street-portfolio-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted State Street institutional investment portfolio management.\"\n      tools:\n        - name: list-portfolios\n          description: >-\n            List all institutional investment portfolios accessible via State Street Alpha.\n            Returns portfolio names, types, base\
  \ currencies, and current market values.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-street-alpha.list-portfolios\"\n          with:\n            portfolioType: \"tools.portfolioType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-portfolio\n          description: >-\n            Get comprehensive details for a specific State Street Alpha portfolio\n            including total market value, benchmark, and custodian information.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-street-alpha.get-portfolio\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-portfolio-positions\n          description: >-\n            List current positions in a portfolio as of a given date. Returns\n           \
  \ securities, quantities, market values, cost basis, and unrealized P&L.\n            Filter by asset class (EQUITY, FIXED_INCOME, CASH, DERIVATIVES, etc.).\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-street-alpha.list-portfolio-positions\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n            asOfDate: \"tools.asOfDate\"\n            assetClass: \"tools.assetClass\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-portfolio-transactions\n          description: >-\n            List transaction history for a portfolio including trades, corporate actions,\n            cash movements, and income events over a specified date range.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-street-alpha.list-portfolio-transactions\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n         \
  \   startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            transactionType: \"tools.transactionType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-portfolio-performance\n          description: >-\n            Get performance measurement data for a portfolio including time-weighted returns,\n            benchmark returns, and active returns over a specified period.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-street-alpha.get-portfolio-performance\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            frequency: \"tools.frequency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-portfolio-risk\n          description: >-\n            Get risk analytics for a portfolio including\
  \ Value at Risk (VaR),\n            tracking error, beta, duration, and factor exposures.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-street-alpha.get-portfolio-risk\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n            asOfDate: \"tools.asOfDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-etf-funds\n          description: >-\n            List ETF funds available for creation and redemption on State Street Fund Connect.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-street-fund-connect.list-funds\"\n          with:\n            market: \"tools.market\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-etf-basket\n          description: >-\n            Get the current portfolio composition basket for an ETF fund showing\n \
  \           the in-kind securities and quantities required per creation unit.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-street-fund-connect.get-fund-basket\"\n          with:\n            fundId: \"tools.fundId\"\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: submit-etf-order\n          description: >-\n            Submit an ETF creation or redemption order through State Street Fund Connect.\n            Specify the fund, order type (CREATION or REDEMPTION), and number of units.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"state-street-fund-connect.create-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-etf-orders\n          description: >-\n            List ETF creation and redemption orders submitted through Fund\
  \ Connect,\n            filterable by fund, status, and date range.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-street-fund-connect.list-orders\"\n          with:\n            fundId: \"tools.fundId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-etf-order-status\n          description: >-\n            Get the current status of a specific ETF creation or redemption order\n            on State Street Fund Connect.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-street-fund-connect.get-order\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-etf-order\n          description: >-\n            Cancel a pending ETF creation or redemption order on State Street Fund\
  \ Connect.\n            Only available for orders in PENDING status.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"state-street-fund-connect.cancel-order\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
