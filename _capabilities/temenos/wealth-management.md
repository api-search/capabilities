---
categories: []
consumed_apis: []
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
- create a new investment portfolio
- list portfolio positions
- cloud banking
- wealth management
- portfolio management
- portfolio valuation
- get portfolio valuation
- place a buy or sell order for a security
- list available securities
- securities trading
- list positions in a portfolio
- list securities
- wealth management clients
- list accounts
- digital banking
- create portfolio
- get account balances for a wealth client's banking account
- fintech
- list portfolios
- securities reference data
- list orders
- list investment portfolios for wealth clients
- financial services
- list clients
- list available securities for investment
- cancel a pending securities order
- list pending and executed security orders
- get client account balances
- get valuation
- client banking accounts (from transact)
- portfolio holdings positions
- list security orders
- get the current market value and performance of a portfolio
- securities order execution
- open banking
- create a new investment portfolio for a client
- private banking
- list current holdings positions in a portfolio
- list investment portfolios
- banking
- list wealth management clients
- place order
- payments
- place a security order
- place security order
- list banking accounts associated with a wealth client
- investment portfolio management
- investment management
- core banking
- cancel security order
- list client accounts
- list client banking accounts
- list positions
slug: wealth-management
source_filename: wealth-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Temenos Wealth Management\n  description: Integrated wealth management workflow combining the Temenos Wealth API and Transact API for portfolio management,\n    securities trading, and client banking. Used by wealth managers and private bankers to manage client portfolios and execute\n    investment strategies.\n  tags:\n  - Wealth Management\n  - Portfolio Management\n  - Securities Trading\n  - Private Banking\n  - Investment Management\n  - Banking\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TEMENOS_WEALTH_TOKEN: TEMENOS_WEALTH_TOKEN\n    TEMENOS_TRANSACT_TOKEN: TEMENOS_TRANSACT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: wealth\n    baseUri: https://api.temenos.com/wealth/v1\n    description: Temenos Wealth API for portfolio and securities management\n    authentication:\n      type: bearer\n      token: '{{TEMENOS_WEALTH_TOKEN}}'\n    resources:\n    - name: portfolios\n\
  \      path: /portfolios\n      description: Investment portfolio management\n      operations:\n      - name: list-portfolios\n        method: GET\n        description: List investment portfolios\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-portfolio\n        method: POST\n        description: Create a new investment portfolio\n        body:\n          type: json\n          data:\n            clientId: '{{tools.clientId}}'\n            portfolioName: '{{tools.portfolioName}}'\n            currency: '{{tools.currency}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolio-positions\n      path: /portfolios/{portfolioId}/positions\n\
  \      description: Portfolio holdings positions\n      operations:\n      - name: list-portfolio-positions\n        method: GET\n        description: List portfolio positions\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portfolio-valuation\n      path: /portfolios/{portfolioId}/valuation\n      description: Portfolio valuation\n      operations:\n      - name: get-portfolio-valuation\n        method: GET\n        description: Get portfolio valuation\n        inputParameters:\n        - name: portfolioId\n          in: path\n          type: string\n          required: true\n          description: Portfolio identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n    - name: security-orders\n      path: /orders/securities\n      description: Securities order management\n      operations:\n      - name: list-security-orders\n        method: GET\n        description: List security orders\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-security-order\n        method: POST\n        description: Place a security order\n        body:\n          type: json\n          data:\n            portfolioId: '{{tools.portfolioId}}'\n            securityId: '{{tools.securityId}}'\n            orderType: '{{tools.orderType}}'\n            quantity: '{{tools.quantity}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n      - name: cancel-security-order\n        method: DELETE\n        description: Cancel a security order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: securities\n      path: /securities\n      description: Securities reference data\n      operations:\n      - name: list-securities\n        method: GET\n        description: List available securities\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: transact\n    baseUri: https://api.temenos.com/transact/v1\n\
  \    description: Temenos Transact core banking API\n    authentication:\n      type: bearer\n      token: '{{TEMENOS_TRANSACT_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /holdings/accounts\n      description: Customer account arrangements\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List customer accounts with optional filtering\n        inputParameters:\n        - name: customerId\n          in: query\n          type: string\n          required: false\n          description: Filter accounts by customer identifier\n        - name: accountType\n          in: query\n          type: string\n          required: false\n          description: Filter by account type (CURRENT, SAVINGS, DEPOSIT, LOAN)\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page\n        - name: page_start\n          in: query\n          type: integer\n        \
  \  required: false\n          description: Starting record number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new account arrangement\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n            accountType: '{{tools.accountType}}'\n            currency: '{{tools.currency}}'\n            productId: '{{tools.productId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-detail\n      path: /holdings/accounts/{accountId}\n      description: Single account operations\n      operations:\n      - name: get-account\n        method: GET\n        description: Get account details\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n     \
  \     required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account\n        method: PUT\n        description: Update account arrangement\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-balances\n      path: /holdings/accounts/{accountId}/balances\n      description: Account balance information\n      operations:\n      - name: get-account-balances\n        method: GET\n        description: Get account balances\n        inputParameters:\n        - name: accountId\n   \
  \       in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-transactions\n      path: /holdings/accounts/{accountId}/transactions\n      description: Account transaction history\n      operations:\n      - name: list-account-transactions\n        method: GET\n        description: List account transactions\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /party/customers\n\
  \      description: Customer management\n      operations:\n      - name: list-customers\n        method: GET\n        description: List customers\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create new customer\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            customerType: '{{tools.customerType}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-detail\n      path: /party/customers/{customerId}\n      description: Single customer\
  \ operations\n      operations:\n      - name: get-customer\n        method: GET\n        description: Get customer details\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-orders\n      path: /order/paymentOrders\n      description: Payment order management\n      operations:\n      - name: list-payment-orders\n        method: GET\n        description: List payment orders\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment-order\n        method: POST\n\
  \        description: Create payment order\n        body:\n          type: json\n          data:\n            debitAccountId: '{{tools.debitAccountId}}'\n            creditAccountId: '{{tools.creditAccountId}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            paymentType: '{{tools.paymentType}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: wealth-management-api\n    description: Unified REST API for Temenos wealth management operations.\n    resources:\n    - path: /v1/portfolios\n      name: portfolios\n      description: Investment portfolio management\n      operations:\n      - method: GET\n        name: list-portfolios\n        description: List investment portfolios\n        call: wealth.list-portfolios\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ POST\n        name: create-portfolio\n        description: Create a new investment portfolio\n        call: wealth.create-portfolio\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios/{portfolioId}/positions\n      name: portfolio-positions\n      description: Portfolio holdings positions\n      operations:\n      - method: GET\n        name: list-positions\n        description: List positions in a portfolio\n        call: wealth.list-portfolio-positions\n        with:\n          portfolioId: rest.portfolioId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios/{portfolioId}/valuation\n      name: portfolio-valuation\n      description: Portfolio valuation\n      operations:\n      - method: GET\n        name: get-valuation\n        description: Get portfolio valuation\n        call: wealth.get-portfolio-valuation\n        with:\n          portfolioId: rest.portfolioId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/securities\n      name: securities\n      description: Securities reference data\n      operations:\n      - method: GET\n        name: list-securities\n        description: List available securities\n        call: wealth.list-securities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/security-orders\n      name: security-orders\n      description: Securities order execution\n      operations:\n      - method: GET\n        name: list-orders\n        description: List security orders\n        call: wealth.list-security-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: place-order\n        description: Place a security order\n        call: wealth.create-security-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clients\n      name: wealth-clients\n      description: Wealth\
  \ management clients\n      operations:\n      - method: GET\n        name: list-clients\n        description: List wealth management clients\n        call: wealth.list-wealth-clients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/client-accounts\n      name: client-accounts\n      description: Client banking accounts (from Transact)\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List client banking accounts\n        call: transact.list-accounts\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: wealth-management-mcp\n    transport: http\n    description: MCP server for AI-assisted wealth management and portfolio operations.\n    tools:\n    - name: list-portfolios\n      description: List investment portfolios for wealth clients\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: wealth.list-portfolios\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-portfolio\n      description: Create a new investment portfolio for a client\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wealth.create-portfolio\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-portfolio-positions\n      description: List current holdings positions in a portfolio\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wealth.list-portfolio-positions\n      with:\n        portfolioId: tools.portfolioId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-portfolio-valuation\n      description: Get the current market value and performance of a portfolio\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wealth.get-portfolio-valuation\n      with:\n        portfolioId:\
  \ tools.portfolioId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-securities\n      description: List available securities for investment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wealth.list-securities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: place-security-order\n      description: Place a buy or sell order for a security\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wealth.create-security-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-security-order\n      description: Cancel a pending securities order\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: wealth.cancel-security-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-security-orders\n\
  \      description: List pending and executed security orders\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wealth.list-security-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-client-accounts\n      description: List banking accounts associated with a wealth client\n      hints:\n        readOnly: true\n        openWorld: false\n      call: transact.list-accounts\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-client-account-balances\n      description: Get account balances for a wealth client's banking account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: transact.get-account-balances\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
