---
categories: []
consumed_apis:
- tango-raas
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
- check the current balance of a reward funding account
- track a specific reward order
- place and track reward deliveries
- list all reward program customers
- register a new reward program customer
- gift cards
- get current exchange rates
- list supported reward delivery countries
- browse the full tango global digital reward catalog with 3,100+ gift cards and incentives
- get reward order
- browse reward catalog
- manage reward funding accounts
- create order
- list reward orders
- get account balance and details
- get account balance
- incentives
- list all reward orders
- manage reward program customers
- list all countries where digital rewards can be delivered
- get account
- view detailed reward delivery records
- send a digital reward to a recipient
- rewards as a service
- browse available digital rewards
- create account
- get order
- send reward
- currency exchange rates for international rewards
- list all reward line items including fulfillment credentials like gift card codes and redemption urls
- digital rewards
- list customers
- list reward orders placed through the account, optionally filtered by date range
- catalog management
- get status and fulfillment details for a specific reward order
- countries where digital rewards are available
- list reward countries
- list all reward program customers in the tango platform
- register a new reward program customer in tango
- list line items
- send a digital gift card or reward to a recipient by email. specify the product utid, amount, recipient name and email, and sender details.
- create customer
- create a reward funding account
- list orders
- list all reward line items with credentials
- get reward order status and fulfillment details
- get exchange rates
- get current currency exchange rates for international reward delivery
- get catalog
- loyalty
- retrieve the full digital reward catalog
slug: reward-automation
source_filename: reward-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tango Reward Automation\"\n  description: >-\n    Workflow capability for automating digital reward and incentive delivery using the\n    Tango RaaS API. Enables loyalty programs, employee recognition platforms, research\n    panels, and consumer incentive applications to send digital gift cards and rewards\n    programmatically. Combines catalog browsing, account management, order placement,\n    and delivery tracking in a unified interface.\n  tags:\n    - Digital Rewards\n    - Gift Cards\n    - Incentives\n    - Loyalty\n    - Rewards As A Service\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TANGO_USERNAME: TANGO_USERNAME\n      TANGO_PASSWORD: TANGO_PASSWORD\n\ncapability:\n  consumes:\n    - import: tango-raas\n      location: ./shared/raas-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tango-reward-automation-api\n      description: \"\
  Unified REST API for automated digital reward and incentive delivery.\"\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: \"Manage reward program customers\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List all reward program customers\"\n              call: \"tango-raas.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Register a new reward program customer\"\n              call: \"tango-raas.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts\n          name: accounts\n          description: \"Manage reward funding accounts\"\n          operations:\n            - method: GET\n              name: get-account\n \
  \             description: \"Get account balance and details\"\n              call: \"tango-raas.get-account\"\n              with:\n                customerIdentifier: \"rest.customerIdentifier\"\n                accountIdentifier: \"rest.accountIdentifier\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n              description: \"Create a reward funding account\"\n              call: \"tango-raas.create-account\"\n              with:\n                customerIdentifier: \"rest.customerIdentifier\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/catalog\n          name: catalog\n          description: \"Browse available digital rewards\"\n          operations:\n            - method: GET\n              name: get-catalog\n              description: \"Retrieve the full digital reward catalog\"\n  \
  \            call: \"tango-raas.get-catalog\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: \"Place and track reward deliveries\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List all reward orders\"\n              call: \"tango-raas.list-orders\"\n              with:\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                elements: \"rest.elements\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-order\n              description: \"Send a digital reward to a recipient\"\n              call: \"tango-raas.create-order\"\n              outputParameters:\n                - type: object\n          \
  \        mapping: \"$.\"\n        - path: /v1/orders/{id}\n          name: order-by-id\n          description: \"Track a specific reward order\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get reward order status and fulfillment details\"\n              call: \"tango-raas.get-order\"\n              with:\n                referenceOrderID: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/line-items\n          name: line-items\n          description: \"View detailed reward delivery records\"\n          operations:\n            - method: GET\n              name: list-line-items\n              description: \"List all reward line items with credentials\"\n              call: \"tango-raas.list-line-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/exchange-rates\n \
  \         name: exchange-rates\n          description: \"Currency exchange rates for international rewards\"\n          operations:\n            - method: GET\n              name: get-exchange-rates\n              description: \"Get current exchange rates\"\n              call: \"tango-raas.get-exchange-rates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reward-countries\n          name: reward-countries\n          description: \"Countries where digital rewards are available\"\n          operations:\n            - method: GET\n              name: list-reward-countries\n              description: \"List supported reward delivery countries\"\n              call: \"tango-raas.list-reward-countries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tango-reward-automation-mcp\n      transport: http\n      description:\
  \ \"MCP server for AI-assisted digital reward and incentive automation.\"\n      tools:\n        - name: list-customers\n          description: \"List all reward program customers in the Tango platform\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tango-raas.list-customers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: \"Register a new reward program customer in Tango\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tango-raas.create-customer\"\n          with:\n            customerIdentifier: \"tools.customerIdentifier\"\n            displayName: \"tools.displayName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-balance\n          description: \"Check the current balance of a reward funding\
  \ account\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tango-raas.get-account\"\n          with:\n            customerIdentifier: \"tools.customerIdentifier\"\n            accountIdentifier: \"tools.accountIdentifier\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: browse-reward-catalog\n          description: \"Browse the full Tango global digital reward catalog with 3,100+ gift cards and incentives\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tango-raas.get-catalog\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-reward\n          description: \"Send a digital gift card or reward to a recipient by email. Specify the product UTID, amount, recipient name and email, and sender details.\"\n          hints:\n \
  \           readOnly: false\n            idempotent: false\n          call: \"tango-raas.create-order\"\n          with:\n            customerIdentifier: \"tools.customerIdentifier\"\n            accountIdentifier: \"tools.accountIdentifier\"\n            amount: \"tools.amount\"\n            utid: \"tools.utid\"\n            recipient: \"tools.recipient\"\n            sender: \"tools.sender\"\n            message: \"tools.message\"\n            sendEmail: \"tools.sendEmail\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reward-orders\n          description: \"List reward orders placed through the account, optionally filtered by date range\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tango-raas.list-orders\"\n          with:\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            elements: \"tools.elements\"\
  \n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-reward-order\n          description: \"Get status and fulfillment details for a specific reward order\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tango-raas.get-order\"\n          with:\n            referenceOrderID: \"tools.referenceOrderID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-line-items\n          description: \"List all reward line items including fulfillment credentials like gift card codes and redemption URLs\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tango-raas.list-line-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-exchange-rates\n\
  \          description: \"Get current currency exchange rates for international reward delivery\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tango-raas.get-exchange-rates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reward-countries\n          description: \"List all countries where digital rewards can be delivered\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"tango-raas.list-reward-countries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
