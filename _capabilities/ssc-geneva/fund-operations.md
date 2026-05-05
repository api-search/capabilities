---
categories: []
consumed_apis:
- ssc-geneva-fund-accounting
description: Unified workflow capability for fund accounting and portfolio management operations using SS&C Geneva. Enables portfolio managers, fund accountants, and operations teams to manage portfolios, process trades, calculate NAV, and report on investor positions across multi-asset fund structures.
layout: capability
name: SS&C Geneva Fund Operations
operations:
- description: List portfolios with optional type, currency, and status filtering
  method: GET
  name: list-portfolios
  path: /v1/portfolios
- description: Get portfolio details including AUM and metadata
  method: GET
  name: get-portfolio
  path: /v1/portfolios/{portfolioId}
- description: Get portfolio positions as of a specific date
  method: GET
  name: get-portfolio-positions
  path: /v1/portfolios/{portfolioId}/positions
- description: List trades for a portfolio in a date range
  method: GET
  name: list-trades
  path: /v1/portfolios/{portfolioId}/trades
- description: Submit a new trade for processing and settlement
  method: POST
  name: create-trade
  path: /v1/portfolios/{portfolioId}/trades
- description: Get NAV calculation for a portfolio on a specific date
  method: GET
  name: get-portfolio-nav
  path: /v1/portfolios/{portfolioId}/nav
- description: List investors with capital allocations for a fund
  method: GET
  name: list-investors
  path: /v1/portfolios/{portfolioId}/investors
personas: []
provider_name: SS&C Geneva
provider_slug: ssc-geneva
search_terms:
- portfolio positions and holdings
- trade capture and processing
- list ss&c geneva fund portfolios with optional filtering by type, currency, and status
- nav calculation
- list portfolios
- list trades for a portfolio within a date range with settlement status
- submit a new trade for processing and settlement
- get portfolio nav
- asset management
- get portfolio
- get nav calculation for a portfolio on a specific date with component breakdown
- hedge funds
- list investors
- get portfolio details including aum and metadata
- investor accounting
- list investors with capital allocations for a fund
- get portfolio positions
- list trades for a portfolio in a date range
- ss&c geneva
- nav calculation and reporting
- list investors in a portfolio with capital balances and ownership percentages
- individual portfolio details
- get ss&c geneva portfolio details including aum, manager, and share classes
- list portfolios with optional type, currency, and status filtering
- portfolio and fund management
- get nav calculation for a portfolio on a specific date
- financial services
- portfolio management
- fund accounting
- create trade
- list trades
- get portfolio positions as of a date with market values and unrealized p&l
- submit a new trade to ss&c geneva for processing and settlement
- get portfolio positions as of a specific date
slug: fund-operations
source_filename: fund-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SS&C Geneva Fund Operations\"\n  description: >-\n    Unified workflow capability for fund accounting and portfolio management\n    operations using SS&C Geneva. Enables portfolio managers, fund accountants,\n    and operations teams to manage portfolios, process trades, calculate NAV,\n    and report on investor positions across multi-asset fund structures.\n  tags:\n    - SS&C Geneva\n    - Fund Accounting\n    - Portfolio Management\n    - Asset Management\n    - Financial Services\n    - NAV Calculation\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SSC_GENEVA_API_TOKEN: SSC_GENEVA_API_TOKEN\n\ncapability:\n  consumes:\n    - import: ssc-geneva-fund-accounting\n      location: ./shared/fund-accounting.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ssc-geneva-fund-operations-api\n      description: \"Unified REST API for SS&C Geneva fund operations.\"\
  \n      resources:\n        - path: /v1/portfolios\n          name: portfolios\n          description: \"Portfolio and fund management\"\n          operations:\n            - method: GET\n              name: list-portfolios\n              description: \"List portfolios with optional type, currency, and status filtering\"\n              call: \"ssc-geneva-fund-accounting.list-portfolios\"\n              with:\n                fundType: \"rest.fundType\"\n                currency: \"rest.currency\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/portfolios/{portfolioId}\n          name: portfolio-detail\n          description: \"Individual portfolio details\"\n          operations:\n            - method: GET\n              name: get-portfolio\n              description: \"Get portfolio details including AUM and metadata\"\n              call: \"ssc-geneva-fund-accounting.get-portfolio\"\
  \n              with:\n                portfolioId: \"rest.portfolioId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/portfolios/{portfolioId}/positions\n          name: positions\n          description: \"Portfolio positions and holdings\"\n          operations:\n            - method: GET\n              name: get-portfolio-positions\n              description: \"Get portfolio positions as of a specific date\"\n              call: \"ssc-geneva-fund-accounting.get-portfolio-positions\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n                asOfDate: \"rest.asOfDate\"\n                assetClass: \"rest.assetClass\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/portfolios/{portfolioId}/trades\n          name: trades\n          description: \"Trade capture and processing\"\n          operations:\n         \
  \   - method: GET\n              name: list-trades\n              description: \"List trades for a portfolio in a date range\"\n              call: \"ssc-geneva-fund-accounting.list-trades\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-trade\n              description: \"Submit a new trade for processing and settlement\"\n              call: \"ssc-geneva-fund-accounting.create-trade\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/portfolios/{portfolioId}/nav\n          name: nav\n          description: \"NAV calculation and reporting\"\n          operations:\n            -\
  \ method: GET\n              name: get-portfolio-nav\n              description: \"Get NAV calculation for a portfolio on a specific date\"\n              call: \"ssc-geneva-fund-accounting.get-portfolio-nav\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n                navDate: \"rest.navDate\"\n                navType: \"rest.navType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/portfolios/{portfolioId}/investors\n          name: investors\n          description: \"Investor accounting\"\n          operations:\n            - method: GET\n              name: list-investors\n              description: \"List investors with capital allocations for a fund\"\n              call: \"ssc-geneva-fund-accounting.list-investors\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n                status: \"rest.status\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ssc-geneva-fund-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SS&C Geneva fund operations and reporting.\"\n      tools:\n        - name: list-portfolios\n          description: \"List SS&C Geneva fund portfolios with optional filtering by type, currency, and status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssc-geneva-fund-accounting.list-portfolios\"\n          with:\n            fundType: \"tools.fundType\"\n            currency: \"tools.currency\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-portfolio\n          description: \"Get SS&C Geneva portfolio details including AUM, manager, and share classes\"\n          hints:\n            readOnly: true\n            idempotent: true\n     \
  \     call: \"ssc-geneva-fund-accounting.get-portfolio\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-portfolio-positions\n          description: \"Get portfolio positions as of a date with market values and unrealized P&L\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssc-geneva-fund-accounting.get-portfolio-positions\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n            asOfDate: \"tools.asOfDate\"\n            assetClass: \"tools.assetClass\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-trades\n          description: \"List trades for a portfolio within a date range with settlement status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssc-geneva-fund-accounting.list-trades\"\
  \n          with:\n            portfolioId: \"tools.portfolioId\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            tradeStatus: \"tools.tradeStatus\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-trade\n          description: \"Submit a new trade to SS&C Geneva for processing and settlement\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ssc-geneva-fund-accounting.create-trade\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-portfolio-nav\n          description: \"Get NAV calculation for a portfolio on a specific date with component breakdown\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssc-geneva-fund-accounting.get-portfolio-nav\"\n          with:\n\
  \            portfolioId: \"tools.portfolioId\"\n            navDate: \"tools.navDate\"\n            navType: \"tools.navType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-investors\n          description: \"List investors in a portfolio with capital balances and ownership percentages\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssc-geneva-fund-accounting.list-investors\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ssc-geneva/refs/heads/main/capabilities/fund-operations.yaml
tags:
- SS&C Geneva
- Fund Accounting
- Portfolio Management
- Asset Management
- Financial Services
- NAV Calculation
tools:
- description: List SS&C Geneva fund portfolios with optional filtering by type, currency, and status
  hints:
    idempotent: true
    readOnly: true
  name: list-portfolios
- description: Get SS&C Geneva portfolio details including AUM, manager, and share classes
  hints:
    idempotent: true
    readOnly: true
  name: get-portfolio
- description: Get portfolio positions as of a date with market values and unrealized P&L
  hints:
    idempotent: true
    readOnly: true
  name: get-portfolio-positions
- description: List trades for a portfolio within a date range with settlement status
  hints:
    idempotent: true
    readOnly: true
  name: list-trades
- description: Submit a new trade to SS&C Geneva for processing and settlement
  hints:
    idempotent: false
    readOnly: false
  name: create-trade
- description: Get NAV calculation for a portfolio on a specific date with component breakdown
  hints:
    idempotent: true
    readOnly: true
  name: get-portfolio-nav
- description: List investors in a portfolio with capital balances and ownership percentages
  hints:
    idempotent: true
    readOnly: true
  name: list-investors
---
