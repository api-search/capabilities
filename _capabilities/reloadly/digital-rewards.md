---
categories: []
consumed_apis:
- reloadly-gift-cards
- reloadly-airtime
description: Unified workflow capability combining Reloadly Gift Cards and Airtime APIs for building digital rewards, loyalty programs, and employee incentive platforms. Enables program managers and marketing teams to discover reward options, check costs, place orders, and track fulfillment across both gift cards and mobile top-ups from a single integration.
layout: capability
name: Reloadly Digital Rewards
operations:
- description: List available gift card products
  method: GET
  name: list-gift-cards
  path: /v1/gift-cards
- description: Get gift card product details
  method: GET
  name: get-gift-card
  path: /v1/gift-cards/{productId}
- description: List gift card discount rates
  method: GET
  name: list-discounts
  path: /v1/discounts
- description: Place a gift card reward order
  method: POST
  name: place-gift-card-order
  path: /v1/orders
- description: Get gift card order and codes
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: List mobile network operators
  method: GET
  name: list-operators
  path: /v1/operators
- description: Send airtime top-up reward
  method: POST
  name: send-topup
  path: /v1/topups
- description: List gift card transactions
  method: GET
  name: list-gift-card-transactions
  path: /v1/transactions
- description: List airtime transactions
  method: GET
  name: list-airtime-transactions
  path: /v1/airtime-transactions
- description: Get gift card account balance
  method: GET
  name: get-gift-card-balance
  path: /v1/balance
personas: []
provider_name: Reloadly
provider_slug: reloadly
search_terms:
- list gift card discounts
- list gift card transactions
- get gift card order and codes
- list gift card discount rates
- send topup
- get gift card account balance
- list airtime top-up transaction history
- gift cards
- check the current account balance for gift card purchases
- list operators
- account balances
- browse the gift card product catalog filtered by country and currency
- list airtime transactions
- retrieve gift card order details and redemption codes
- get gift card product details
- get gift card balance
- individual gift card order
- rewards
- all reward transactions
- automatically identify the mobile operator for a phone number
- get account balance
- order a digital gift card reward for a recipient
- get gift card order
- incentives
- list gift card products
- send airtime topup
- payments
- place a gift card reward order
- list gift cards
- gift card orders
- get order
- individual gift card product
- send a mobile airtime top-up reward to a phone number
- airtime
- list gift card order transaction history
- list available gift card products
- get gift card product
- digital rewards
- list mobile network operators
- airtime top-up orders
- airtime top-up transactions
- get details for a specific gift card product including denominations
- auto detect operator
- mobile network operators for airtime
- available discount rates on gift cards
- reloadly
- place gift card order
- mobile top-up
- gift card product catalog
- send airtime top-up reward
- get gift card
- browse mobile network operators for airtime top-ups by country
- list discounts
- list discount rates available on gift card products
- loyalty
slug: digital-rewards
source_filename: digital-rewards.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Reloadly Digital Rewards\n  description: >-\n    Unified workflow capability combining Reloadly Gift Cards and Airtime APIs\n    for building digital rewards, loyalty programs, and employee incentive\n    platforms. Enables program managers and marketing teams to discover\n    reward options, check costs, place orders, and track fulfillment across\n    both gift cards and mobile top-ups from a single integration.\n  tags:\n    - Reloadly\n    - Digital Rewards\n    - Gift Cards\n    - Airtime\n    - Loyalty\n    - Incentives\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RELOADLY_CLIENT_ID: RELOADLY_CLIENT_ID\n      RELOADLY_CLIENT_SECRET: RELOADLY_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: reloadly-gift-cards\n      location: ./shared/gift-cards.yaml\n    - import: reloadly-airtime\n      location: ./shared/airtime.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8080\n      namespace: reloadly-rewards-api\n      description: \"Unified REST API for digital rewards program management.\"\n      resources:\n        - path: /v1/gift-cards\n          name: gift-cards\n          description: Gift card product catalog\n          operations:\n            - method: GET\n              name: list-gift-cards\n              description: List available gift card products\n              call: \"reloadly-gift-cards.list-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gift-cards/{productId}\n          name: gift-card\n          description: Individual gift card product\n          operations:\n            - method: GET\n              name: get-gift-card\n              description: Get gift card product details\n              call: \"reloadly-gift-cards.get-product\"\n              with:\n                productId: \"rest.productId\"\n              outputParameters:\n          \
  \      - type: object\n                  mapping: \"$.\"\n        - path: /v1/discounts\n          name: discounts\n          description: Available discount rates on gift cards\n          operations:\n            - method: GET\n              name: list-discounts\n              description: List gift card discount rates\n              call: \"reloadly-gift-cards.list-discounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: Gift card orders\n          operations:\n            - method: POST\n              name: place-gift-card-order\n              description: Place a gift card reward order\n              call: \"reloadly-gift-cards.place-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{orderId}\n          name: order\n          description: Individual gift card order\n \
  \         operations:\n            - method: GET\n              name: get-order\n              description: Get gift card order and codes\n              call: \"reloadly-gift-cards.get-order\"\n              with:\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/operators\n          name: operators\n          description: Mobile network operators for airtime\n          operations:\n            - method: GET\n              name: list-operators\n              description: List mobile network operators\n              call: \"reloadly-airtime.list-operators\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/topups\n          name: topups\n          description: Airtime top-up orders\n          operations:\n            - method: POST\n              name: send-topup\n              description: Send airtime top-up\
  \ reward\n              call: \"reloadly-airtime.send-topup\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transactions\n          name: transactions\n          description: All reward transactions\n          operations:\n            - method: GET\n              name: list-gift-card-transactions\n              description: List gift card transactions\n              call: \"reloadly-gift-cards.list-transactions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/airtime-transactions\n          name: airtime-transactions\n          description: Airtime top-up transactions\n          operations:\n            - method: GET\n              name: list-airtime-transactions\n              description: List airtime transactions\n              call: \"reloadly-airtime.list-topup-transactions\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/balance\n          name: balance\n          description: Account balances\n          operations:\n            - method: GET\n              name: get-gift-card-balance\n              description: Get gift card account balance\n              call: \"reloadly-gift-cards.get-balance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: reloadly-rewards-mcp\n      transport: http\n      description: \"MCP server for AI-assisted digital rewards program management.\"\n      tools:\n        - name: list-gift-card-products\n          description: Browse the gift card product catalog filtered by country and currency\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reloadly-gift-cards.list-products\"\n          with:\n            countryCode: \"tools.countryCode\"\n            currencyCode: \"tools.currencyCode\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-gift-card-product\n          description: Get details for a specific gift card product including denominations\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reloadly-gift-cards.get-product\"\n          with:\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-gift-card-discounts\n          description: List discount rates available on gift card products\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reloadly-gift-cards.list-discounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: place-gift-card-order\n          description: Order a digital gift card reward for a recipient\n          hints:\n            readOnly: false\n    \
  \        destructive: false\n          call: \"reloadly-gift-cards.place-order\"\n          with:\n            productId: \"tools.productId\"\n            quantity: \"tools.quantity\"\n            unitPrice: \"tools.unitPrice\"\n            senderName: \"tools.senderName\"\n            recipientEmail: \"tools.recipientEmail\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-gift-card-order\n          description: Retrieve gift card order details and redemption codes\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"reloadly-gift-cards.get-order\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-operators\n          description: Browse mobile network operators for airtime top-ups by country\n          hints:\n            readOnly: true\n            openWorld: true\n \
  \         call: \"reloadly-airtime.list-operators\"\n          with:\n            countryCode: \"tools.countryCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: auto-detect-operator\n          description: Automatically identify the mobile operator for a phone number\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"reloadly-airtime.auto-detect-operator\"\n          with:\n            phone: \"tools.phone\"\n            countryCode: \"tools.countryCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-airtime-topup\n          description: Send a mobile airtime top-up reward to a phone number\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"reloadly-airtime.send-topup\"\n          with:\n            operatorId: \"tools.operatorId\"\n            amount: \"tools.amount\"\n   \
  \         useLocalAmount: \"tools.useLocalAmount\"\n            customIdentifier: \"tools.customIdentifier\"\n            recipientPhone: \"tools.recipientPhone\"\n            senderPhone: \"tools.senderPhone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-gift-card-transactions\n          description: List gift card order transaction history\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"reloadly-gift-cards.list-transactions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-airtime-transactions\n          description: List airtime top-up transaction history\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"reloadly-airtime.list-topup-transactions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-balance\n\
  \          description: Check the current account balance for gift card purchases\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"reloadly-gift-cards.get-balance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/reloadly/refs/heads/main/capabilities/digital-rewards.yaml
tags:
- Reloadly
- Digital Rewards
- Gift Cards
- Airtime
- Loyalty
- Incentives
tools:
- description: Browse the gift card product catalog filtered by country and currency
  hints:
    openWorld: true
    readOnly: true
  name: list-gift-card-products
- description: Get details for a specific gift card product including denominations
  hints:
    openWorld: true
    readOnly: true
  name: get-gift-card-product
- description: List discount rates available on gift card products
  hints:
    openWorld: true
    readOnly: true
  name: list-gift-card-discounts
- description: Order a digital gift card reward for a recipient
  hints:
    destructive: false
    readOnly: false
  name: place-gift-card-order
- description: Retrieve gift card order details and redemption codes
  hints:
    openWorld: false
    readOnly: true
  name: get-gift-card-order
- description: Browse mobile network operators for airtime top-ups by country
  hints:
    openWorld: true
    readOnly: true
  name: list-operators
- description: Automatically identify the mobile operator for a phone number
  hints:
    openWorld: true
    readOnly: true
  name: auto-detect-operator
- description: Send a mobile airtime top-up reward to a phone number
  hints:
    destructive: false
    readOnly: false
  name: send-airtime-topup
- description: List gift card order transaction history
  hints:
    openWorld: false
    readOnly: true
  name: list-gift-card-transactions
- description: List airtime top-up transaction history
  hints:
    openWorld: false
    readOnly: true
  name: list-airtime-transactions
- description: Check the current account balance for gift card purchases
  hints:
    openWorld: false
    readOnly: true
  name: get-account-balance
---
