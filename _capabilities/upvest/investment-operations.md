---
categories: []
consumed_apis: []
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
- financial instruments and prices
- list direct debits
- create webhook subscription
- retrieve user
- retrieve details for a specific user by id
- place order
- retrieve order details
- individual account operations
- order placement and management
- cancel a pending order before execution
- list instruments
- reports and transaction data
- funding and withdrawal operations
- savings plans
- set up a direct debit payment for account funding
- list investment reports and statements
- upvest
- cancel a pending order
- list all orders across accounts
- list positions
- register a new webhook endpoint for event notifications
- list withdrawals
- retrieve a specific account
- create account
- cash withdrawal operations
- create a new investment account for a user
- get current and historical account valuations
- portfolio creation, allocation, and rebalancing
- Integration Engineer
- create a new investment account
- list all orders
- list all investment accounts
- get price data for a specific financial instrument
- account positions and valuations
- administrator managing the investment platform configuration and reporting
- create user
- cancel order
- engineer integrating upvest apis into banking or wealth management platforms
- onboard a new user
- process a withdrawal
- register a webhook
- investments
- list valuations
- individual order operations
- Fintech Developer
- list all accounts
- create a portfolio
- list orders
- list available financial instruments (stocks, etfs, mutual funds)
- fractional investing
- list transactions
- create a direct debit
- list all investment portfolios
- list all onboarded users on the investment platform
- retrieve details and status for a specific order
- portfolio management
- user onboarding and management
- order placement, execution, and instrument data
- create webhook
- list account positions
- list savings plans
- place a buy or sell order
- portfolios
- onboard a new user to the investment platform
- full investment lifecycle management for embedded investment products
- list webhook subscriptions
- trading
- individual user operations
- investment account management
- securities
- wealth management
- automated savings plan management
- user onboarding, identity verification, and compliance
- place a buy or sell order for a financial instrument
- investment account creation and lifecycle
- Investment Platform Admin
- webhook subscription management
- custody
- create an automated recurring investment savings plan
- retrieve order
- retrieve details for a specific investment account
- retrieve a specific user
- list all automated savings plans
- list investment reports
- list transaction history for accounts
- create direct debit
- banking infrastructure
- create withdrawal
- list available instruments
- list reports
- developer building embedded investment features into a fintech app
- create portfolio
- list transaction history
- retrieve account
- transactions, reports, fees, and compliance
- list instrument prices
- direct debit payments
- list all registered webhook subscriptions
- create savings plan
- create a new investment portfolio with custom allocations
- list portfolios
- list all onboarded users
- list users
- list accounts
- list current investment positions and holdings for an account
- list webhooks
- process a cash withdrawal from an investment account
- create a savings plan
- fintech
slug: investment-operations
source_filename: investment-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Upvest Investment Operations\n  description: Unified workflow capability for building and managing investment experiences on the Upvest platform. Covers\n    user onboarding, account management, order placement, portfolio management, savings plans, and position tracking. Designed\n    for fintech developers and integration engineers building embedded investment features.\n  tags:\n  - Upvest\n  - Investments\n  - Fintech\n  - Banking Infrastructure\n  - Trading\n  - Portfolios\n  - Savings Plans\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UPVEST_CLIENT_ID: UPVEST_CLIENT_ID\n    UPVEST_CLIENT_SECRET: UPVEST_CLIENT_SECRET\n    UPVEST_ACCESS_TOKEN: UPVEST_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: upvest-investment\n    baseUri: https://api.upvest.co\n    description: Upvest Investment API for building embedded investment experiences.\n    authentication:\n      type:\
  \ bearer\n      token: '{{UPVEST_ACCESS_TOKEN}}'\n    resources:\n    - name: authentication\n      path: /auth/token\n      description: OAuth 2.0 token management\n      operations:\n      - name: create-access-token\n        method: POST\n        description: Obtain an OAuth 2.0 access token using client credentials\n        inputParameters:\n        - name: grant_type\n          in: body\n          type: string\n          required: true\n          description: Must be client_credentials\n        - name: client_id\n          in: body\n          type: string\n          required: true\n          description: Client identifier\n        - name: client_secret\n          in: body\n          type: string\n          required: true\n          description: Client secret\n        - name: scope\n          in: body\n          type: string\n          required: true\n          description: Space-separated scopes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: users\n      path: /users\n      description: End user management\n      operations:\n      - name: list-users\n        method: GET\n        description: Retrieve a paginated list of all onboarded users\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Onboard a new user to the investment platform\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            email: '{{tools.email}}'\n            date_of_birth: '{{tools.date_of_birth}}'\n            nationality: '{{tools.nationality}}'\n      - name: retrieve-user\n        method: GET\n        description: Retrieve details for a specific user\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PATCH\n        description: Update profile information for an existing user\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: accounts\n      path: /accounts\n      description: Investment account management\n      operations:\n      - name: list-accounts\n        method: GET\n        description: Retrieve all investment accounts\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new investment account\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n    \
  \      data:\n            user_id: '{{tools.user_id}}'\n            account_group_id: '{{tools.account_group_id}}'\n      - name: retrieve-account\n        method: GET\n        description: Retrieve a specific investment account\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: close-account\n        method: DELETE\n        description: Close an investment account\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instruments\n      path: /instruments\n      description: Financial instruments\
  \ and price data\n      operations:\n      - name: list-instruments\n        method: GET\n        description: List available financial instruments\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: retrieve-instrument\n        method: GET\n        description: Retrieve a specific instrument\n        inputParameters:\n        - name: instrument_id\n          in: path\n          type: string\n          required: true\n          description: Instrument UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-instrument-prices\n\
  \        method: GET\n        description: Retrieve real-time and historical price data\n        inputParameters:\n        - name: instrument_id\n          in: path\n          type: string\n          required: true\n          description: Instrument UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Order placement and management\n      operations:\n      - name: list-orders\n        method: GET\n        description: List all orders\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n      - name: place-order\n        method: POST\n        description: Place a new buy or sell order\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account_id: '{{tools.account_id}}'\n            instrument_id: '{{tools.instrument_id}}'\n            side: '{{tools.side}}'\n            amount: '{{tools.amount}}'\n      - name: retrieve-order\n        method: GET\n        description: Retrieve a specific order\n        inputParameters:\n        - name: order_id\n          in: path\n          type: string\n          required: true\n          description: Order UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-order\n        method: DELETE\n        description: Cancel a pending order\n        inputParameters:\n\
  \        - name: order_id\n          in: path\n          type: string\n          required: true\n          description: Order UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolios\n      path: /portfolios\n      description: Portfolio management\n      operations:\n      - name: list-portfolios\n        method: GET\n        description: List all portfolios\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-portfolio\n        method: POST\n        description: Create a new portfolio\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            account_id: '{{tools.account_id}}'\n      - name: retrieve-portfolio\n        method: GET\n        description: Retrieve a specific portfolio\n        inputParameters:\n        - name: portfolio_id\n          in: path\n          type: string\n          required: true\n          description: Portfolio UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: savings-plans\n      path: /savings_plans\n      description: Automated savings plan management\n      operations:\n      - name: list-savings-plans\n        method: GET\n        description: List all savings plans\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n      - name: create-savings-plan\n        method: POST\n        description: Create a new savings plan\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account_id: '{{tools.account_id}}'\n            amount: '{{tools.amount}}'\n            frequency: '{{tools.frequency}}'\n      - name: update-savings-plan\n        method: PATCH\n        description: Update a savings plan\n        inputParameters:\n        - name: savings_plan_id\n          in: path\n          type: string\n          required: true\n          description: Savings plan UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-savings-plan\n        method: DELETE\n        description: Delete\
  \ a savings plan\n        inputParameters:\n        - name: savings_plan_id\n          in: path\n          type: string\n          required: true\n          description: Savings plan UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments\n      path: /payments\n      description: Payment operations including top-ups, withdrawals, and direct debits\n      operations:\n      - name: create-direct-debit\n        method: POST\n        description: Create a direct debit payment\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account_id: '{{tools.account_id}}'\n            amount: '{{tools.amount}}'\n      - name: list-direct-debits\n        method: GET\n        description: List direct debit operations\n        inputParameters:\n\
  \        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-withdrawal\n        method: POST\n        description: Process a cash withdrawal\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account_id: '{{tools.account_id}}'\n            amount: '{{tools.amount}}'\n      - name: list-withdrawals\n        method: GET\n        description: List withdrawal operations\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: positions\n      path: /positions\n      description: Account position and valuation data\n      operations:\n      - name: list-positions\n        method: GET\n        description: List current holdings for an account\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-valuations\n        method: GET\n        description: List account valuations\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-returns\n \
  \       method: GET\n        description: List investment returns for an account\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /webhooks\n      description: Webhook subscription management\n      operations:\n      - name: list-webhook-subscriptions\n        method: GET\n        description: List all webhook subscriptions\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook-subscription\n        method: POST\n        description: Register a new webhook endpoint\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            events: '{{tools.events}}'\n      - name: retrieve-webhook-subscription\n        method: GET\n        description: Retrieve a specific webhook subscription\n        inputParameters:\n        - name: webhook_id\n          in: path\n          type: string\n          required: true\n          description: Webhook UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-webhook-subscription\n        method: DELETE\n        description: Delete a webhook subscription\n        inputParameters:\n        - name: webhook_id\n          in: path\n          type: string\n          required: true\n          description: Webhook UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n\
  \      path: /reports\n      description: Reporting and transaction data\n      operations:\n      - name: list-reports\n        method: GET\n        description: List user-facing investment reports\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-transactions\n        method: GET\n        description: List transaction history\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-fees\n        method: GET\n        description: List fee charges on accounts\n        inputParameters:\n\
  \        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: upvest-investment-ops-api\n    description: Unified REST API for Upvest investment operations.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User onboarding and management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all onboarded users\n        call: upvest-investment.list-users\n        with:\n          offset: rest.offset\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Onboard a new user\n        call: upvest-investment.create-user\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/users/{user_id}\n      name: user\n      description: Individual user operations\n      operations:\n      - method: GET\n        name: retrieve-user\n        description: Retrieve a specific user\n        call: upvest-investment.retrieve-user\n        with:\n          user_id: rest.user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: Investment account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all accounts\n        call: upvest-investment.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-account\n        description: Create a new investment account\n        call: upvest-investment.create-account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{account_id}\n\
  \      name: account\n      description: Individual account operations\n      operations:\n      - method: GET\n        name: retrieve-account\n        description: Retrieve a specific account\n        call: upvest-investment.retrieve-account\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Order placement and management\n      operations:\n      - method: GET\n        name: list-orders\n        description: List all orders\n        call: upvest-investment.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: place-order\n        description: Place a buy or sell order\n        call: upvest-investment.place-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{order_id}\n      name: order\n      description: Individual order operations\n\
  \      operations:\n      - method: GET\n        name: retrieve-order\n        description: Retrieve order details\n        call: upvest-investment.retrieve-order\n        with:\n          order_id: rest.order_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-order\n        description: Cancel a pending order\n        call: upvest-investment.cancel-order\n        with:\n          order_id: rest.order_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instruments\n      name: instruments\n      description: Financial instruments and prices\n      operations:\n      - method: GET\n        name: list-instruments\n        description: List available instruments\n        call: upvest-investment.list-instruments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios\n      name: portfolios\n      description: Portfolio management\n\
  \      operations:\n      - method: GET\n        name: list-portfolios\n        description: List portfolios\n        call: upvest-investment.list-portfolios\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-portfolio\n        description: Create a portfolio\n        call: upvest-investment.create-portfolio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/savings-plans\n      name: savings-plans\n      description: Automated savings plan management\n      operations:\n      - method: GET\n        name: list-savings-plans\n        description: List savings plans\n        call: upvest-investment.list-savings-plans\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-savings-plan\n        description: Create a savings plan\n        call: upvest-investment.create-savings-plan\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/positions\n      name: positions\n      description: Account positions and valuations\n      operations:\n      - method: GET\n        name: list-positions\n        description: List account positions\n        call: upvest-investment.list-positions\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/direct-debits\n      name: direct-debits\n      description: Direct debit payments\n      operations:\n      - method: POST\n        name: create-direct-debit\n        description: Create a direct debit\n        call: upvest-investment.create-direct-debit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-direct-debits\n        description: List direct debits\n        call: upvest-investment.list-direct-debits\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/payments/withdrawals\n      name: withdrawals\n      description: Cash withdrawal operations\n      operations:\n      - method: POST\n        name: create-withdrawal\n        description: Process a withdrawal\n        call: upvest-investment.create-withdrawal\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-withdrawals\n        description: List withdrawals\n        call: upvest-investment.list-withdrawals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Webhook subscription management\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List webhook subscriptions\n        call: upvest-investment.list-webhook-subscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Register\
  \ a webhook\n        call: upvest-investment.create-webhook-subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Reports and transaction data\n      operations:\n      - method: GET\n        name: list-reports\n        description: List investment reports\n        call: upvest-investment.list-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-transactions\n        description: List transaction history\n        call: upvest-investment.list-transactions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: upvest-investment-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted investment operations on the Upvest platform.\n    tools:\n    - name: list-users\n      description: List all onboarded users on the investment platform\n   \
  \   hints:\n        readOnly: true\n        openWorld: true\n      call: upvest-investment.list-users\n      with:\n        offset: tools.offset\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Onboard a new user to the investment platform\n      hints:\n        readOnly: false\n      call: upvest-investment.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieve-user\n      description: Retrieve details for a specific user by ID\n      hints:\n        readOnly: true\n      call: upvest-investment.retrieve-user\n      with:\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounts\n      description: List all investment accounts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upvest-investment.list-accounts\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: create-account\n      description: Create a new investment account for a user\n      hints:\n        readOnly: false\n      call: upvest-investment.create-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieve-account\n      description: Retrieve details for a specific investment account\n      hints:\n        readOnly: true\n      call: upvest-investment.retrieve-account\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-instruments\n      description: List available financial instruments (stocks, ETFs, mutual funds)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upvest-investment.list-instruments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-instrument-prices\n      description: Get price data for a specific financial instrument\n      hints:\n        readOnly:\
  \ true\n      call: upvest-investment.list-instrument-prices\n      with:\n        instrument_id: tools.instrument_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List all orders across accounts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upvest-investment.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: place-order\n      description: Place a buy or sell order for a financial instrument\n      hints:\n        readOnly: false\n      call: upvest-investment.place-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieve-order\n      description: Retrieve details and status for a specific order\n      hints:\n        readOnly: true\n      call: upvest-investment.retrieve-order\n      with:\n        order_id: tools.order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-order\n\
  \      description: Cancel a pending order before execution\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: upvest-investment.cancel-order\n      with:\n        order_id: tools.order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-portfolios\n      description: List all investment portfolios\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upvest-investment.list-portfolios\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-portfolio\n      description: Create a new investment portfolio with custom allocations\n      hints:\n        readOnly: false\n      call: upvest-investment.create-portfolio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-savings-plans\n      description: List all automated savings plans\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upvest-investment.list-savings-plans\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-savings-plan\n      description: Create an automated recurring investment savings plan\n      hints:\n        readOnly: false\n      call: upvest-investment.create-savings-plan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-positions\n      description: List current investment positions and holdings for an account\n      hints:\n        readOnly: true\n      call: upvest-investment.list-positions\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-valuations\n      description: Get current and historical account valuations\n      hints:\n        readOnly: true\n      call: upvest-investment.list-valuations\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-direct-debit\n      description: Set\
  \ up a direct debit payment for account funding\n      hints:\n        readOnly: false\n      call: upvest-investment.create-direct-debit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-withdrawal\n      description: Process a cash withdrawal from an investment account\n      hints:\n        readOnly: false\n      call: upvest-investment.create-withdrawal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List investment reports and statements\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upvest-investment.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-transactions\n      description: List transaction history for accounts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upvest-investment.list-transactions\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: list-webhook-subscriptions\n      description: List all registered webhook subscriptions\n      hints:\n        readOnly: true\n      call: upvest-investment.list-webhook-subscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook-subscription\n      description: Register a new webhook endpoint for event notifications\n      hints:\n        readOnly: false\n      call: upvest-investment.create-webhook-subscription\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
