---
categories: []
consumed_apis:
- wealth
- transact
description: Integrated wealth management workflow combining the Temenos Wealth API and Transact API for portfolio management, securities trading, and client banking. Used by wealth managers and private bankers to manage client portfolios and execute investment strategies.
layout: capability
name: Temenos Wealth Management
operations:
- description: List investment portfolios
  method: GET
  name: list-portfolios
  path: /v1/portfolios
- description: Create a new investment portfolio
  method: POST
  name: create-portfolio
  path: /v1/portfolios
- description: List positions in a portfolio
  method: GET
  name: list-positions
  path: /v1/portfolios/{portfolioId}/positions
- description: Get portfolio valuation
  method: GET
  name: get-valuation
  path: /v1/portfolios/{portfolioId}/valuation
- description: List available securities
  method: GET
  name: list-securities
  path: /v1/securities
- description: List security orders
  method: GET
  name: list-orders
  path: /v1/security-orders
- description: Place a security order
  method: POST
  name: place-order
  path: /v1/security-orders
- description: List wealth management clients
  method: GET
  name: list-clients
  path: /v1/clients
- description: List client banking accounts
  method: GET
  name: list-accounts
  path: /v1/client-accounts
personas: []
provider_name: Temenos
provider_slug: temenos
search_terms:
- cancel a pending securities order
- place a security order
- wealth management clients
- investment portfolio management
- cancel security order
- list banking accounts associated with a wealth client
- investment management
- place a buy or sell order for a security
- wealth management
- securities order execution
- create a new investment portfolio for a client
- place order
- get portfolio valuation
- digital banking
- place security order
- financial services
- list client accounts
- open banking
- get valuation
- banking
- list available securities
- cloud banking
- list portfolios
- list investment portfolios
- core banking
- payments
- list positions
- list client banking accounts
- list portfolio positions
- securities trading
- create a new investment portfolio
- list available securities for investment
- list accounts
- securities reference data
- private banking
- list pending and executed security orders
- get account balances for a wealth client's banking account
- list securities
- client banking accounts (from transact)
- portfolio valuation
- get client account balances
- portfolio management
- list current holdings positions in a portfolio
- portfolio holdings positions
- list orders
- fintech
- list security orders
- list wealth management clients
- get the current market value and performance of a portfolio
- list clients
- create portfolio
- list positions in a portfolio
- list investment portfolios for wealth clients
slug: wealth-management
source_filename: wealth-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Temenos Wealth Management\"\n  description: \"Integrated wealth management workflow combining the Temenos Wealth API and Transact API for portfolio management, securities trading, and client banking. Used by wealth managers and private bankers to manage client portfolios and execute investment strategies.\"\n  tags:\n    - Wealth Management\n    - Portfolio Management\n    - Securities Trading\n    - Private Banking\n    - Investment Management\n    - Banking\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TEMENOS_WEALTH_TOKEN: TEMENOS_WEALTH_TOKEN\n      TEMENOS_TRANSACT_TOKEN: TEMENOS_TRANSACT_TOKEN\n\ncapability:\n  consumes:\n    - import: wealth\n      location: ./shared/wealth.yaml\n    - import: transact\n      location: ./shared/transact.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: wealth-management-api\n      description: \"Unified REST\
  \ API for Temenos wealth management operations.\"\n      resources:\n        - path: /v1/portfolios\n          name: portfolios\n          description: \"Investment portfolio management\"\n          operations:\n            - method: GET\n              name: list-portfolios\n              description: \"List investment portfolios\"\n              call: \"wealth.list-portfolios\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-portfolio\n              description: \"Create a new investment portfolio\"\n              call: \"wealth.create-portfolio\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}/positions\n          name: portfolio-positions\n          description: \"Portfolio holdings positions\"\n          operations:\n            - method: GET\n              name: list-positions\n\
  \              description: \"List positions in a portfolio\"\n              call: \"wealth.list-portfolio-positions\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portfolios/{portfolioId}/valuation\n          name: portfolio-valuation\n          description: \"Portfolio valuation\"\n          operations:\n            - method: GET\n              name: get-valuation\n              description: \"Get portfolio valuation\"\n              call: \"wealth.get-portfolio-valuation\"\n              with:\n                portfolioId: \"rest.portfolioId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/securities\n          name: securities\n          description: \"Securities reference data\"\n          operations:\n            - method: GET\n              name: list-securities\n\
  \              description: \"List available securities\"\n              call: \"wealth.list-securities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/security-orders\n          name: security-orders\n          description: \"Securities order execution\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List security orders\"\n              call: \"wealth.list-security-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: place-order\n              description: \"Place a security order\"\n              call: \"wealth.create-security-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/clients\n          name: wealth-clients\n          description: \"Wealth management clients\"\
  \n          operations:\n            - method: GET\n              name: list-clients\n              description: \"List wealth management clients\"\n              call: \"wealth.list-wealth-clients\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/client-accounts\n          name: client-accounts\n          description: \"Client banking accounts (from Transact)\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List client banking accounts\"\n              call: \"transact.list-accounts\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: wealth-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted wealth management and portfolio operations.\"\n\
  \      tools:\n        - name: list-portfolios\n          description: \"List investment portfolios for wealth clients\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wealth.list-portfolios\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-portfolio\n          description: \"Create a new investment portfolio for a client\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wealth.create-portfolio\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-portfolio-positions\n          description: \"List current holdings positions in a portfolio\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wealth.list-portfolio-positions\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n      \
  \    outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-portfolio-valuation\n          description: \"Get the current market value and performance of a portfolio\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wealth.get-portfolio-valuation\"\n          with:\n            portfolioId: \"tools.portfolioId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-securities\n          description: \"List available securities for investment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wealth.list-securities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: place-security-order\n          description: \"Place a buy or sell order for a security\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent:\
  \ false\n          call: \"wealth.create-security-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-security-order\n          description: \"Cancel a pending securities order\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"wealth.cancel-security-order\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-security-orders\n          description: \"List pending and executed security orders\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wealth.list-security-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-client-accounts\n          description: \"List banking accounts associated with a wealth client\"\n       \
  \   hints:\n            readOnly: true\n            openWorld: false\n          call: \"transact.list-accounts\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-client-account-balances\n          description: \"Get account balances for a wealth client's banking account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"transact.get-account-balances\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/temenos/refs/heads/main/capabilities/wealth-management.yaml
tags:
- Wealth Management
- Portfolio Management
- Securities Trading
- Private Banking
- Investment Management
- Banking
tools:
- description: List investment portfolios for wealth clients
  hints:
    openWorld: false
    readOnly: true
  name: list-portfolios
- description: Create a new investment portfolio for a client
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-portfolio
- description: List current holdings positions in a portfolio
  hints:
    openWorld: false
    readOnly: true
  name: list-portfolio-positions
- description: Get the current market value and performance of a portfolio
  hints:
    openWorld: true
    readOnly: true
  name: get-portfolio-valuation
- description: List available securities for investment
  hints:
    openWorld: true
    readOnly: true
  name: list-securities
- description: Place a buy or sell order for a security
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: place-security-order
- description: Cancel a pending securities order
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-security-order
- description: List pending and executed security orders
  hints:
    openWorld: false
    readOnly: true
  name: list-security-orders
- description: List banking accounts associated with a wealth client
  hints:
    openWorld: false
    readOnly: true
  name: list-client-accounts
- description: Get account balances for a wealth client's banking account
  hints:
    openWorld: false
    readOnly: true
  name: get-client-account-balances
---
