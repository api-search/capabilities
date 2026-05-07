---
categories: []
consumed_apis: []
description: Workflow capability for automating digital reward and incentive delivery using the Tango RaaS API. Enables loyalty programs, employee recognition platforms, research panels, and consumer incentive applications to send digital gift cards and rewards programmatically. Combines catalog browsing, account management, order placement, and delivery tracking in a unified interface.
layout: capability
name: Tango Reward Automation
operations:
- description: List all reward program customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Register a new reward program customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get account balance and details
  method: GET
  name: get-account
  path: /v1/accounts
- description: Create a reward funding account
  method: POST
  name: create-account
  path: /v1/accounts
- description: Retrieve the full digital reward catalog
  method: GET
  name: get-catalog
  path: /v1/catalog
- description: List all reward orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Send a digital reward to a recipient
  method: POST
  name: create-order
  path: /v1/orders
- description: Get reward order status and fulfillment details
  method: GET
  name: get-order
  path: /v1/orders/{id}
- description: List all reward line items with credentials
  method: GET
  name: list-line-items
  path: /v1/line-items
- description: Get current exchange rates
  method: GET
  name: get-exchange-rates
  path: /v1/exchange-rates
- description: List supported reward delivery countries
  method: GET
  name: list-reward-countries
  path: /v1/reward-countries
personas: []
provider_name: Tango
provider_slug: tango
search_terms:
- register a new reward program customer in tango
- currency exchange rates for international rewards
- get account
- list all countries where digital rewards can be delivered
- create customer
- get status and fulfillment details for a specific reward order
- list all reward program customers
- get reward order
- create order
- list line items
- list all reward line items with credentials
- loyalty
- list reward orders
- send a digital reward to a recipient
- get reward order status and fulfillment details
- create a reward funding account
- track a specific reward order
- list all reward program customers in the tango platform
- check the current balance of a reward funding account
- browse reward catalog
- digital rewards
- register a new reward program customer
- get account balance
- list all reward orders
- view detailed reward delivery records
- get exchange rates
- list all reward line items including fulfillment credentials like gift card codes and redemption urls
- send a digital gift card or reward to a recipient by email. specify the product utid, amount, recipient name and email, and sender details.
- list supported reward delivery countries
- list orders
- create account
- gift cards
- get current exchange rates
- list reward orders placed through the account, optionally filtered by date range
- browse the full tango global digital reward catalog with 3,100+ gift cards and incentives
- place and track reward deliveries
- manage reward program customers
- list reward countries
- list customers
- retrieve the full digital reward catalog
- browse available digital rewards
- send reward
- get account balance and details
- countries where digital rewards are available
- manage reward funding accounts
- get current currency exchange rates for international reward delivery
- incentives
- rewards as a service
- get catalog
- catalog management
- get order
slug: reward-automation
source_filename: reward-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tango Reward Automation\n  description: Workflow capability for automating digital reward and incentive delivery using the Tango RaaS API. Enables\n    loyalty programs, employee recognition platforms, research panels, and consumer incentive applications to send digital\n    gift cards and rewards programmatically. Combines catalog browsing, account management, order placement, and delivery\n    tracking in a unified interface.\n  tags:\n  - Digital Rewards\n  - Gift Cards\n  - Incentives\n  - Loyalty\n  - Rewards As A Service\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TANGO_USERNAME: TANGO_USERNAME\n    TANGO_PASSWORD: TANGO_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: tango-raas\n    baseUri: https://api.tangocard.com/raas/v2\n    description: Tango RaaS API v2 for rewards and incentive automation\n    authentication:\n      type: basic\n      username: '{{TANGO_USERNAME}}'\n\
  \      password: '{{TANGO_PASSWORD}}'\n    resources:\n    - name: customers\n      path: /customers\n      description: Manage customer accounts in the Tango platform\n      operations:\n      - name: list-customers\n        method: GET\n        description: Retrieve all customers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create a new customer account\n        body:\n          type: json\n          data:\n            customerIdentifier: '{{tools.customerIdentifier}}'\n            displayName: '{{tools.displayName}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-by-id\n      path: /customers/{customerIdentifier}\n      description: Manage a specific customer\n      operations:\n      - name: get-customer\n        method: GET\n\
  \        description: Get customer details\n        inputParameters:\n        - name: customerIdentifier\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /customers/{customerIdentifier}/accounts\n      description: Manage accounts for a customer\n      operations:\n      - name: list-customer-accounts\n        method: GET\n        description: List all accounts for a customer\n        inputParameters:\n        - name: customerIdentifier\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new account\
  \ for a customer\n        inputParameters:\n        - name: customerIdentifier\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        body:\n          type: json\n          data:\n            accountIdentifier: '{{tools.accountIdentifier}}'\n            displayName: '{{tools.displayName}}'\n            currencyCode: '{{tools.currencyCode}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-by-id\n      path: /customers/{customerIdentifier}/accounts/{accountIdentifier}\n      description: Manage a specific account\n      operations:\n      - name: get-account\n        method: GET\n        description: Get account details including current balance\n        inputParameters:\n        - name: customerIdentifier\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n  \
  \      - name: accountIdentifier\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalog\n      path: /catalogs\n      description: Access the global digital reward catalog\n      operations:\n      - name: get-catalog\n        method: GET\n        description: Retrieve the full reward catalog\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Place and manage reward orders\n      operations:\n      - name: list-orders\n        method: GET\n        description: List all reward orders\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Filter orders from this\
  \ date\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: Filter orders up to this date\n        - name: elements\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: Place a new reward order\n        body:\n          type: json\n          data:\n            customerIdentifier: '{{tools.customerIdentifier}}'\n            accountIdentifier: '{{tools.accountIdentifier}}'\n            amount: '{{tools.amount}}'\n            utid: '{{tools.utid}}'\n            recipient: '{{tools.recipient}}'\n            sender: '{{tools.sender}}'\n\
  \            message: '{{tools.message}}'\n            sendEmail: '{{tools.sendEmail}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: order-by-id\n      path: /orders/{referenceOrderID}\n      description: Manage a specific order\n      operations:\n      - name: get-order\n        method: GET\n        description: Get order details\n        inputParameters:\n        - name: referenceOrderID\n          in: path\n          type: string\n          required: true\n          description: Order reference ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: line-items\n      path: /lineItems\n      description: View and manage order line items\n      operations:\n      - name: list-line-items\n        method: GET\n        description: List all order line items\n        inputParameters:\n        - name: startDate\n\
  \          in: query\n          type: string\n          required: false\n          description: Filter from date\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: Filter to date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exchange-rates\n      path: /exchangerates\n      description: Reference data - currency exchange rates\n      operations:\n      - name: get-exchange-rates\n        method: GET\n        description: Get current exchange rates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reward-countries\n      path: /rewardCountries\n      description: Reference data - countries where rewards are available\n      operations:\n      - name: list-reward-countries\n        method: GET\n        description: List all countries where\
  \ rewards can be delivered\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tango-reward-automation-api\n    description: Unified REST API for automated digital reward and incentive delivery.\n    resources:\n    - path: /v1/customers\n      name: customers\n      description: Manage reward program customers\n      operations:\n      - method: GET\n        name: list-customers\n        description: List all reward program customers\n        call: tango-raas.list-customers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Register a new reward program customer\n        call: tango-raas.create-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: Manage reward\
  \ funding accounts\n      operations:\n      - method: GET\n        name: get-account\n        description: Get account balance and details\n        call: tango-raas.get-account\n        with:\n          customerIdentifier: rest.customerIdentifier\n          accountIdentifier: rest.accountIdentifier\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-account\n        description: Create a reward funding account\n        call: tango-raas.create-account\n        with:\n          customerIdentifier: rest.customerIdentifier\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalog\n      name: catalog\n      description: Browse available digital rewards\n      operations:\n      - method: GET\n        name: get-catalog\n        description: Retrieve the full digital reward catalog\n        call: tango-raas.get-catalog\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/orders\n      name: orders\n      description: Place and track reward deliveries\n      operations:\n      - method: GET\n        name: list-orders\n        description: List all reward orders\n        call: tango-raas.list-orders\n        with:\n          startDate: rest.startDate\n          endDate: rest.endDate\n          elements: rest.elements\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Send a digital reward to a recipient\n        call: tango-raas.create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{id}\n      name: order-by-id\n      description: Track a specific reward order\n      operations:\n      - method: GET\n        name: get-order\n        description: Get reward order status and fulfillment details\n        call: tango-raas.get-order\n        with:\n        \
  \  referenceOrderID: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/line-items\n      name: line-items\n      description: View detailed reward delivery records\n      operations:\n      - method: GET\n        name: list-line-items\n        description: List all reward line items with credentials\n        call: tango-raas.list-line-items\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/exchange-rates\n      name: exchange-rates\n      description: Currency exchange rates for international rewards\n      operations:\n      - method: GET\n        name: get-exchange-rates\n        description: Get current exchange rates\n        call: tango-raas.get-exchange-rates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reward-countries\n      name: reward-countries\n      description: Countries where digital rewards are available\n      operations:\n      - method:\
  \ GET\n        name: list-reward-countries\n        description: List supported reward delivery countries\n        call: tango-raas.list-reward-countries\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tango-reward-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted digital reward and incentive automation.\n    tools:\n    - name: list-customers\n      description: List all reward program customers in the Tango platform\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: tango-raas.list-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Register a new reward program customer in Tango\n      hints:\n        readOnly: false\n        idempotent: false\n      call: tango-raas.create-customer\n      with:\n        customerIdentifier: tools.customerIdentifier\n      \
  \  displayName: tools.displayName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-balance\n      description: Check the current balance of a reward funding account\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: tango-raas.get-account\n      with:\n        customerIdentifier: tools.customerIdentifier\n        accountIdentifier: tools.accountIdentifier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-reward-catalog\n      description: Browse the full Tango global digital reward catalog with 3,100+ gift cards and incentives\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: tango-raas.get-catalog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-reward\n      description: Send a digital gift card or reward to a recipient by email. Specify the product UTID, amount, recipient\n\
  \        name and email, and sender details.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: tango-raas.create-order\n      with:\n        customerIdentifier: tools.customerIdentifier\n        accountIdentifier: tools.accountIdentifier\n        amount: tools.amount\n        utid: tools.utid\n        recipient: tools.recipient\n        sender: tools.sender\n        message: tools.message\n        sendEmail: tools.sendEmail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reward-orders\n      description: List reward orders placed through the account, optionally filtered by date range\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: tango-raas.list-orders\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n        elements: tools.elements\n        offset: tools.offset\n      outputParameters:\n      - type: object\n        mapping: $.\n  \
  \  - name: get-reward-order\n      description: Get status and fulfillment details for a specific reward order\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: tango-raas.get-order\n      with:\n        referenceOrderID: tools.referenceOrderID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-line-items\n      description: List all reward line items including fulfillment credentials like gift card codes and redemption URLs\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: tango-raas.list-line-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-exchange-rates\n      description: Get current currency exchange rates for international reward delivery\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: tango-raas.get-exchange-rates\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: list-reward-countries\n      description: List all countries where digital rewards can be delivered\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: tango-raas.list-reward-countries\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tango/refs/heads/main/capabilities/reward-automation.yaml
tags:
- Digital Rewards
- Gift Cards
- Incentives
- Loyalty
- Rewards As A Service
tools:
- description: List all reward program customers in the Tango platform
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-customers
- description: Register a new reward program customer in Tango
  hints:
    idempotent: false
    readOnly: false
  name: create-customer
- description: Check the current balance of a reward funding account
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-account-balance
- description: Browse the full Tango global digital reward catalog with 3,100+ gift cards and incentives
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: browse-reward-catalog
- description: Send a digital gift card or reward to a recipient by email. Specify the product UTID, amount, recipient name and email, and sender details.
  hints:
    idempotent: false
    readOnly: false
  name: send-reward
- description: List reward orders placed through the account, optionally filtered by date range
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-reward-orders
- description: Get status and fulfillment details for a specific reward order
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-reward-order
- description: List all reward line items including fulfillment credentials like gift card codes and redemption URLs
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-line-items
- description: Get current currency exchange rates for international reward delivery
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-exchange-rates
- description: List all countries where digital rewards can be delivered
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-reward-countries
---
