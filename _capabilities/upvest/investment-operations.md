---
categories: []
consumed_apis:
- upvest-investment
description: Unified workflow capability for building and managing investment experiences on the Upvest platform. Covers user onboarding, account management, order placement, portfolio management, savings plans, and position tracking. Designed for fintech developers and integration engineers building embedded investment features.
layout: capability
name: Upvest Investment Operations
operations:
- description: List all onboarded users
  method: GET
  name: list-users
  path: /v1/users
- description: Onboard a new user
  method: POST
  name: create-user
  path: /v1/users
- description: Retrieve a specific user
  method: GET
  name: retrieve-user
  path: /v1/users/{user_id}
- description: List all accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Create a new investment account
  method: POST
  name: create-account
  path: /v1/accounts
- description: Retrieve a specific account
  method: GET
  name: retrieve-account
  path: /v1/accounts/{account_id}
- description: List all orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Place a buy or sell order
  method: POST
  name: place-order
  path: /v1/orders
- description: Retrieve order details
  method: GET
  name: retrieve-order
  path: /v1/orders/{order_id}
- description: Cancel a pending order
  method: DELETE
  name: cancel-order
  path: /v1/orders/{order_id}
- description: List available instruments
  method: GET
  name: list-instruments
  path: /v1/instruments
- description: List portfolios
  method: GET
  name: list-portfolios
  path: /v1/portfolios
- description: Create a portfolio
  method: POST
  name: create-portfolio
  path: /v1/portfolios
- description: List savings plans
  method: GET
  name: list-savings-plans
  path: /v1/savings-plans
- description: Create a savings plan
  method: POST
  name: create-savings-plan
  path: /v1/savings-plans
- description: List account positions
  method: GET
  name: list-positions
  path: /v1/positions
- description: Create a direct debit
  method: POST
  name: create-direct-debit
  path: /v1/payments/direct-debits
- description: List direct debits
  method: GET
  name: list-direct-debits
  path: /v1/payments/direct-debits
- description: Process a withdrawal
  method: POST
  name: create-withdrawal
  path: /v1/payments/withdrawals
- description: List withdrawals
  method: GET
  name: list-withdrawals
  path: /v1/payments/withdrawals
- description: List webhook subscriptions
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Register a webhook
  method: POST
  name: create-webhook
  path: /v1/webhooks
- description: List investment reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: List transaction history
  method: GET
  name: list-transactions
  path: /v1/reports
personas: []
provider_name: Upvest
provider_slug: upvest
search_terms:
- automated savings plan management
- list users
- transactions, reports, fees, and compliance
- register a new webhook endpoint for event notifications
- list positions
- list instruments
- administrator managing the investment platform configuration and reporting
- individual order operations
- create webhook
- list all orders
- create a new investment account for a user
- wealth management
- developer building embedded investment features into a fintech app
- onboard a new user
- place a buy or sell order
- list all automated savings plans
- get price data for a specific financial instrument
- list current investment positions and holdings for an account
- trading
- get current and historical account valuations
- fractional investing
- place a buy or sell order for a financial instrument
- list reports
- list webhooks
- process a withdrawal
- cancel a pending order
- create webhook subscription
- list all investment portfolios
- list savings plans
- upvest
- financial instruments and prices
- list all onboarded users on the investment platform
- investments
- fintech
- list all onboarded users
- account positions and valuations
- full investment lifecycle management for embedded investment products
- retrieve order details
- portfolios
- create withdrawal
- list instrument prices
- cancel order
- create a new investment account
- individual user operations
- funding and withdrawal operations
- engineer integrating upvest apis into banking or wealth management platforms
- list valuations
- list webhook subscriptions
- list transaction history for accounts
- retrieve order
- securities
- list all registered webhook subscriptions
- list account positions
- user onboarding, identity verification, and compliance
- list withdrawals
- list investment reports
- create direct debit
- user onboarding and management
- create an automated recurring investment savings plan
- list available instruments
- process a cash withdrawal from an investment account
- create account
- direct debit payments
- reports and transaction data
- cancel a pending order before execution
- investment account creation and lifecycle
- create a savings plan
- list all investment accounts
- cash withdrawal operations
- create a new investment portfolio with custom allocations
- order placement, execution, and instrument data
- custody
- retrieve details for a specific investment account
- list orders
- create savings plan
- onboard a new user to the investment platform
- retrieve details and status for a specific order
- list all accounts
- list available financial instruments (stocks, etfs, mutual funds)
- Fintech Developer
- portfolio management
- list portfolios
- retrieve a specific account
- retrieve user
- list accounts
- create user
- order placement and management
- place order
- create a direct debit
- savings plans
- create portfolio
- webhook subscription management
- retrieve details for a specific user by id
- create a portfolio
- investment account management
- portfolio creation, allocation, and rebalancing
- list all orders across accounts
- list investment reports and statements
- banking infrastructure
- retrieve a specific user
- list transactions
- list transaction history
- Investment Platform Admin
- retrieve account
- list direct debits
- register a webhook
- individual account operations
- set up a direct debit payment for account funding
- Integration Engineer
slug: investment-operations
source_filename: investment-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Upvest Investment Operations\"\n  description: \"Unified workflow capability for building and managing investment experiences on the Upvest platform. Covers user onboarding, account management, order placement, portfolio management, savings plans, and position tracking. Designed for fintech developers and integration engineers building embedded investment features.\"\n  tags:\n    - Upvest\n    - Investments\n    - Fintech\n    - Banking Infrastructure\n    - Trading\n    - Portfolios\n    - Savings Plans\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UPVEST_CLIENT_ID: UPVEST_CLIENT_ID\n      UPVEST_CLIENT_SECRET: UPVEST_CLIENT_SECRET\n      UPVEST_ACCESS_TOKEN: UPVEST_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: upvest-investment\n      location: ./shared/investment-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: upvest-investment-ops-api\n\
  \      description: \"Unified REST API for Upvest investment operations.\"\n      resources:\n        - path: /v1/users\n          name: users\n          description: \"User onboarding and management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all onboarded users\"\n              call: \"upvest-investment.list-users\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Onboard a new user\"\n              call: \"upvest-investment.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{user_id}\n          name: user\n          description: \"Individual user operations\"\n          operations:\n\
  \            - method: GET\n              name: retrieve-user\n              description: \"Retrieve a specific user\"\n              call: \"upvest-investment.retrieve-user\"\n              with:\n                user_id: \"rest.user_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts\n          name: accounts\n          description: \"Investment account management\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List all accounts\"\n              call: \"upvest-investment.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n              description: \"Create a new investment account\"\n              call: \"upvest-investment.create-account\"\n              outputParameters:\n                - type: object\n \
  \                 mapping: \"$.\"\n        - path: /v1/accounts/{account_id}\n          name: account\n          description: \"Individual account operations\"\n          operations:\n            - method: GET\n              name: retrieve-account\n              description: \"Retrieve a specific account\"\n              call: \"upvest-investment.retrieve-account\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: \"Order placement and management\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List all orders\"\n              call: \"upvest-investment.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: place-order\n  \
  \            description: \"Place a buy or sell order\"\n              call: \"upvest-investment.place-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{order_id}\n          name: order\n          description: \"Individual order operations\"\n          operations:\n            - method: GET\n              name: retrieve-order\n              description: \"Retrieve order details\"\n              call: \"upvest-investment.retrieve-order\"\n              with:\n                order_id: \"rest.order_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-order\n              description: \"Cancel a pending order\"\n              call: \"upvest-investment.cancel-order\"\n              with:\n                order_id: \"rest.order_id\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/instruments\n          name: instruments\n          description: \"Financial instruments and prices\"\n          operations:\n            - method: GET\n              name: list-instruments\n              description: \"List available instruments\"\n              call: \"upvest-investment.list-instruments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/portfolios\n          name: portfolios\n          description: \"Portfolio management\"\n          operations:\n            - method: GET\n              name: list-portfolios\n              description: \"List portfolios\"\n              call: \"upvest-investment.list-portfolios\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-portfolio\n              description: \"Create a portfolio\"\n             \
  \ call: \"upvest-investment.create-portfolio\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/savings-plans\n          name: savings-plans\n          description: \"Automated savings plan management\"\n          operations:\n            - method: GET\n              name: list-savings-plans\n              description: \"List savings plans\"\n              call: \"upvest-investment.list-savings-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-savings-plan\n              description: \"Create a savings plan\"\n              call: \"upvest-investment.create-savings-plan\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/positions\n          name: positions\n          description: \"Account positions and valuations\"\n          operations:\n\
  \            - method: GET\n              name: list-positions\n              description: \"List account positions\"\n              call: \"upvest-investment.list-positions\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments/direct-debits\n          name: direct-debits\n          description: \"Direct debit payments\"\n          operations:\n            - method: POST\n              name: create-direct-debit\n              description: \"Create a direct debit\"\n              call: \"upvest-investment.create-direct-debit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-direct-debits\n              description: \"List direct debits\"\n              call: \"upvest-investment.list-direct-debits\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments/withdrawals\n          name: withdrawals\n          description: \"Cash withdrawal operations\"\n          operations:\n            - method: POST\n              name: create-withdrawal\n              description: \"Process a withdrawal\"\n              call: \"upvest-investment.create-withdrawal\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-withdrawals\n              description: \"List withdrawals\"\n              call: \"upvest-investment.list-withdrawals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n          description: \"Webhook subscription management\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List\
  \ webhook subscriptions\"\n              call: \"upvest-investment.list-webhook-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"Register a webhook\"\n              call: \"upvest-investment.create-webhook-subscription\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: \"Reports and transaction data\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List investment reports\"\n              call: \"upvest-investment.list-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-transactions\n              description: \"List transaction\
  \ history\"\n              call: \"upvest-investment.list-transactions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: upvest-investment-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted investment operations on the Upvest platform.\"\n      tools:\n        - name: list-users\n          description: \"List all onboarded users on the investment platform\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"upvest-investment.list-users\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Onboard a new user to the investment platform\"\n          hints:\n            readOnly: false\n          call: \"upvest-investment.create-user\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: retrieve-user\n          description: \"Retrieve details for a specific user by ID\"\n          hints:\n            readOnly: true\n          call: \"upvest-investment.retrieve-user\"\n          with:\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-accounts\n          description: \"List all investment accounts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"upvest-investment.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-account\n          description: \"Create a new investment account for a user\"\n          hints:\n            readOnly: false\n          call: \"upvest-investment.create-account\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: retrieve-account\n          description: \"Retrieve details for a specific investment account\"\n          hints:\n            readOnly: true\n          call: \"upvest-investment.retrieve-account\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-instruments\n          description: \"List available financial instruments (stocks, ETFs, mutual funds)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"upvest-investment.list-instruments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-instrument-prices\n          description: \"Get price data for a specific financial instrument\"\n          hints:\n            readOnly: true\n          call: \"upvest-investment.list-instrument-prices\"\n          with:\n          \
  \  instrument_id: \"tools.instrument_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-orders\n          description: \"List all orders across accounts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"upvest-investment.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: place-order\n          description: \"Place a buy or sell order for a financial instrument\"\n          hints:\n            readOnly: false\n          call: \"upvest-investment.place-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: retrieve-order\n          description: \"Retrieve details and status for a specific order\"\n          hints:\n            readOnly: true\n          call: \"upvest-investment.retrieve-order\"\n          with:\n            order_id: \"tools.order_id\"\n \
  \         outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-order\n          description: \"Cancel a pending order before execution\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"upvest-investment.cancel-order\"\n          with:\n            order_id: \"tools.order_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-portfolios\n          description: \"List all investment portfolios\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"upvest-investment.list-portfolios\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-portfolio\n          description: \"Create a new investment portfolio with custom allocations\"\n          hints:\n            readOnly: false\n          call: \"upvest-investment.create-portfolio\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-savings-plans\n          description: \"List all automated savings plans\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"upvest-investment.list-savings-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-savings-plan\n          description: \"Create an automated recurring investment savings plan\"\n          hints:\n            readOnly: false\n          call: \"upvest-investment.create-savings-plan\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-positions\n          description: \"List current investment positions and holdings for an account\"\n          hints:\n            readOnly: true\n          call: \"upvest-investment.list-positions\"\n          with:\n            account_id: \"tools.account_id\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-valuations\n          description: \"Get current and historical account valuations\"\n          hints:\n            readOnly: true\n          call: \"upvest-investment.list-valuations\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-direct-debit\n          description: \"Set up a direct debit payment for account funding\"\n          hints:\n            readOnly: false\n          call: \"upvest-investment.create-direct-debit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-withdrawal\n          description: \"Process a cash withdrawal from an investment account\"\n          hints:\n            readOnly: false\n          call: \"upvest-investment.create-withdrawal\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-reports\n          description: \"List investment reports and statements\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"upvest-investment.list-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-transactions\n          description: \"List transaction history for accounts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"upvest-investment.list-transactions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhook-subscriptions\n          description: \"List all registered webhook subscriptions\"\n          hints:\n            readOnly: true\n          call: \"upvest-investment.list-webhook-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: create-webhook-subscription\n          description: \"Register a new webhook endpoint for event notifications\"\n          hints:\n            readOnly: false\n          call: \"upvest-investment.create-webhook-subscription\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/upvest/refs/heads/main/capabilities/investment-operations.yaml
tags:
- Upvest
- Investments
- Fintech
- Banking Infrastructure
- Trading
- Portfolios
- Savings Plans
tools:
- description: List all onboarded users on the investment platform
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Onboard a new user to the investment platform
  hints:
    readOnly: false
  name: create-user
- description: Retrieve details for a specific user by ID
  hints:
    readOnly: true
  name: retrieve-user
- description: List all investment accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-accounts
- description: Create a new investment account for a user
  hints:
    readOnly: false
  name: create-account
- description: Retrieve details for a specific investment account
  hints:
    readOnly: true
  name: retrieve-account
- description: List available financial instruments (stocks, ETFs, mutual funds)
  hints:
    openWorld: true
    readOnly: true
  name: list-instruments
- description: Get price data for a specific financial instrument
  hints:
    readOnly: true
  name: list-instrument-prices
- description: List all orders across accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Place a buy or sell order for a financial instrument
  hints:
    readOnly: false
  name: place-order
- description: Retrieve details and status for a specific order
  hints:
    readOnly: true
  name: retrieve-order
- description: Cancel a pending order before execution
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: cancel-order
- description: List all investment portfolios
  hints:
    openWorld: true
    readOnly: true
  name: list-portfolios
- description: Create a new investment portfolio with custom allocations
  hints:
    readOnly: false
  name: create-portfolio
- description: List all automated savings plans
  hints:
    openWorld: true
    readOnly: true
  name: list-savings-plans
- description: Create an automated recurring investment savings plan
  hints:
    readOnly: false
  name: create-savings-plan
- description: List current investment positions and holdings for an account
  hints:
    readOnly: true
  name: list-positions
- description: Get current and historical account valuations
  hints:
    readOnly: true
  name: list-valuations
- description: Set up a direct debit payment for account funding
  hints:
    readOnly: false
  name: create-direct-debit
- description: Process a cash withdrawal from an investment account
  hints:
    readOnly: false
  name: create-withdrawal
- description: List investment reports and statements
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: List transaction history for accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-transactions
- description: List all registered webhook subscriptions
  hints:
    readOnly: true
  name: list-webhook-subscriptions
- description: Register a new webhook endpoint for event notifications
  hints:
    readOnly: false
  name: create-webhook-subscription
---
