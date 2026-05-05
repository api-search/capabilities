---
api_specs:
- filename: veli-openapi.yml
  format: yaml
  label: veli
  slug: veli
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/veli/refs/heads/main/openapi/veli-openapi.yml
categories: []
consumed_apis:
- veli
description: Customer workflow capability for crypto investment strategy management. Combines strategy discovery, portfolio creation, automated rebalancing, position tracking, and performance reporting into a unified interface for fintech platforms, crypto exchanges, and robo-advisor applications.
layout: capability
name: Crypto Investment Workflow
operations:
- description: List available crypto investment strategies filtered by category and risk level
  method: GET
  name: list-strategies
  path: /v1/strategies
- description: Get strategy details including allocations and historical performance
  method: GET
  name: get-strategy
  path: /v1/strategies/{strategyId}
- description: List portfolios for a user or filtered by strategy
  method: GET
  name: list-portfolios
  path: /v1/portfolios
- description: Create a new investment portfolio based on a strategy
  method: POST
  name: create-portfolio
  path: /v1/portfolios
- description: Get portfolio details including status and current value
  method: GET
  name: get-portfolio
  path: /v1/portfolios/{portfolioId}
- description: Close and liquidate an investment portfolio
  method: DELETE
  name: close-portfolio
  path: /v1/portfolios/{portfolioId}
- description: Get current asset positions with quantities and market values
  method: GET
  name: get-positions
  path: /v1/portfolios/{portfolioId}/positions
- description: Trigger a rebalance to restore target strategy allocations
  method: POST
  name: rebalance-portfolio
  path: /v1/portfolios/{portfolioId}/rebalance
- description: Get portfolio performance metrics and returns for a time period
  method: GET
  name: get-performance
  path: /v1/portfolios/{portfolioId}/performance
personas: []
provider_name: Veli
provider_slug: veli
search_terms:
- get full details for a specific crypto investment strategy including asset allocations and performance history
- get current asset positions in a portfolio with quantities, prices, and market values
- list portfolios
- get portfolio performance metrics
- investment
- get current portfolio details including status, total value, and strategy information
- get positions
- list strategies
- trigger a rebalance to restore target strategy allocations
- get portfolio
- defi
- trigger portfolio rebalancing
- get strategy
- finance
- create portfolio
- get portfolio performance metrics and returns for a time period
- create a new crypto investment portfolio for a user based on a chosen strategy and initial investment amount
- trigger a portfolio rebalance to restore target asset allocations defined by the investment strategy
- rebalance portfolio
- get details for a specific investment strategy
- get portfolio details including status and current value
- list investment portfolios for a user or filtered by strategy
- get performance
- get strategy details including allocations and historical performance
- list available crypto investment strategies filtered by category and risk level
- create a new investment portfolio based on a strategy
- get portfolio performance metrics including returns, gains/losses, and allocation for a time period (1d, 7d, 30d, 90d, 1y, all)
- close portfolio
- browse available crypto investment strategies, optionally filtered by category (index, theme, custom) or risk level (low, medium, high)
- get current asset positions with quantities and market values
- list portfolios for a user or filtered by strategy
- manage investment portfolios
- browse available crypto investment strategies
- close and liquidate an investment portfolio
- get or close a specific portfolio
- portfolio management
- crypto
- view current asset positions in a portfolio
slug: crypto-investment
source_filename: crypto-investment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Crypto Investment Workflow\"\n  description: >-\n    Customer workflow capability for crypto investment strategy management. Combines\n    strategy discovery, portfolio creation, automated rebalancing, position tracking,\n    and performance reporting into a unified interface for fintech platforms, crypto\n    exchanges, and robo-advisor applications.\n  tags:\n    - Crypto\n    - DeFi\n    - Finance\n    - Investment\n    - Portfolio Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VELI_API_KEY: VELI_API_KEY\n\ncapability:\n  consumes:\n    - import: veli\n      location: ./shared/veli.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: crypto-investment-api\n      description: \"Unified REST API for crypto investment strategy and portfolio management workflows.\"\n      resources:\n        - path: /v1/strategies\n          name: strategies\n\
  \          description: \"Browse available crypto investment strategies\"\n          operations:\n            - method: GET\n              name: list-strategies\n              description: \"List available crypto investment strategies filtered by category and risk level\"\n              call: \"veli.list-strategies\"\n              with:\n                category: \"rest.category\"\n                risk: \"rest.risk\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/strategies/{strategyId}\n          name: strategy\n          description: \"Get details for a specific investment strategy\"\n          operations:\n            - method: GET\n              name: get-strategy\n              description: \"Get strategy details including allocations and historical performance\"\n              call: \"veli.get-strategy\"\n              with:\n\
  \                strategyId: \"rest.strategyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portfolios\n          name: portfolios\n          description: \"Manage investment portfolios\"\n          operations:\n            - method: GET\n              name: list-portfolios\n              description: \"List portfolios for a user or filtered by strategy\"\n              call: \"veli.list-portfolios\"\n              with:\n                userId: \"rest.userId\"\n                strategyId: \"rest.strategyId\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-portfolio\n              description: \"Create a new investment portfolio based on a strategy\"\n              call: \"veli.create-portfolio\"\n              with:\n   \
  \             body: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}\n          name: portfolio\n          description: \"Get or close a specific portfolio\"\n          operations:\n            - method: GET\n              name: get-portfolio\n              description: \"Get portfolio details including status and current value\"\n              call: \"veli.get-portfolio\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: close-portfolio\n              description: \"Close and liquidate an investment portfolio\"\n              call: \"veli.close-portfolio\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}/positions\n          name: positions\n          description: \"View current asset positions in a portfolio\"\n          operations:\n            - method: GET\n              name: get-positions\n              description: \"Get current asset positions with quantities and market values\"\n              call: \"veli.get-positions\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}/rebalance\n          name: rebalance\n          description: \"Trigger portfolio rebalancing\"\n          operations:\n            - method: POST\n              name: rebalance-portfolio\n              description: \"Trigger a rebalance to restore target strategy allocations\"\n              call: \"veli.rebalance-portfolio\"\n              with:\n                portfolioId:\
  \ \"rest.portfolioId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}/performance\n          name: performance\n          description: \"Get portfolio performance metrics\"\n          operations:\n            - method: GET\n              name: get-performance\n              description: \"Get portfolio performance metrics and returns for a time period\"\n              call: \"veli.get-performance\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: crypto-investment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted crypto investment strategy and portfolio management.\"\n      tools:\n        - name: list-strategies\n          description: \"Browse\
  \ available crypto investment strategies, optionally filtered by category (index, theme, custom) or risk level (low, medium, high)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"veli.list-strategies\"\n          with:\n            category: \"tools.category\"\n            risk: \"tools.risk\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-strategy\n          description: \"Get full details for a specific crypto investment strategy including asset allocations and performance history\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"veli.get-strategy\"\n          with:\n            strategyId: \"tools.strategyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-portfolios\n          description:\
  \ \"List investment portfolios for a user or filtered by strategy\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"veli.list-portfolios\"\n          with:\n            userId: \"tools.userId\"\n            strategyId: \"tools.strategyId\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-portfolio\n          description: \"Create a new crypto investment portfolio for a user based on a chosen strategy and initial investment amount\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"veli.create-portfolio\"\n          with:\n            userId: \"tools.userId\"\n            strategyId: \"tools.strategyId\"\n            initialAmount: \"tools.initialAmount\"\n            currency: \"tools.currency\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n\n        - name: get-portfolio\n          description: \"Get current portfolio details including status, total value, and strategy information\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"veli.get-portfolio\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-positions\n          description: \"Get current asset positions in a portfolio with quantities, prices, and market values\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"veli.get-positions\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: rebalance-portfolio\n          description: \"Trigger a portfolio rebalance to restore target asset allocations defined by\
  \ the investment strategy\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"veli.rebalance-portfolio\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-performance\n          description: \"Get portfolio performance metrics including returns, gains/losses, and allocation for a time period (1d, 7d, 30d, 90d, 1y, all)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"veli.get-performance\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n            period: \"tools.period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/veli/refs/heads/main/capabilities/crypto-investment.yaml
tags:
- Crypto
- DeFi
- Finance
- Investment
- Portfolio Management
tools:
- description: Browse available crypto investment strategies, optionally filtered by category (index, theme, custom) or risk level (low, medium, high)
  hints:
    openWorld: false
    readOnly: true
  name: list-strategies
- description: Get full details for a specific crypto investment strategy including asset allocations and performance history
  hints:
    openWorld: false
    readOnly: true
  name: get-strategy
- description: List investment portfolios for a user or filtered by strategy
  hints:
    openWorld: false
    readOnly: true
  name: list-portfolios
- description: Create a new crypto investment portfolio for a user based on a chosen strategy and initial investment amount
  hints:
    openWorld: false
    readOnly: false
  name: create-portfolio
- description: Get current portfolio details including status, total value, and strategy information
  hints:
    openWorld: false
    readOnly: true
  name: get-portfolio
- description: Get current asset positions in a portfolio with quantities, prices, and market values
  hints:
    openWorld: false
    readOnly: true
  name: get-positions
- description: Trigger a portfolio rebalance to restore target asset allocations defined by the investment strategy
  hints:
    openWorld: false
    readOnly: false
  name: rebalance-portfolio
- description: Get portfolio performance metrics including returns, gains/losses, and allocation for a time period (1d, 7d, 30d, 90d, 1y, all)
  hints:
    openWorld: false
    readOnly: true
  name: get-performance
---
