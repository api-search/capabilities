---
categories: []
consumed_apis:
- payouts-api
description: Workflow capability for digital reward and gift card distribution using the Runa platform. Combines product discovery, order management, balance monitoring, and cost estimation for B2C payment, employee incentive, customer loyalty, and marketing reward workflows. Serves reward program managers, growth engineers, and operations teams automating digital reward delivery at scale.
layout: capability
name: Runa Rewards Distribution
operations:
- description: Browse available gift cards and payout products
  method: GET
  name: browse-catalog
  path: /v1/catalog
- description: List product categories for catalog filtering
  method: GET
  name: list-categories
  path: /v1/catalog/categories
- description: List countries supported by Runa
  method: GET
  name: list-countries
  path: /v1/catalog/countries
- description: Get product denominations and redemption info
  method: GET
  name: get-product
  path: /v1/catalog/{productId}
- description: Create and send a digital reward to a recipient
  method: POST
  name: send-reward
  path: /v1/rewards
- description: List all reward orders
  method: GET
  name: list-rewards
  path: /v1/rewards
- description: Get reward order status and payout URL
  method: GET
  name: get-reward-status
  path: /v1/rewards/{orderId}
- description: Estimate cost before sending a reward
  method: POST
  name: estimate-reward
  path: /v1/rewards/estimate
- description: Get current account balance
  method: GET
  name: get-balance
  path: /v1/account/balance
personas: []
provider_name: Runa
provider_slug: runa
search_terms:
- get denomination options and redemption instructions for a specific runa product
- list rewards
- get product details
- list product categories for catalog filtering
- estimate reward
- list countries
- list all reward orders
- get reward status
- list all product categories available in the runa catalog (e.g., retail, dining, gaming)
- send reward
- list countries supported by runa
- browse catalog
- loyalty
- gift cards
- create and send a digital reward to a recipient
- get balance
- get the current runa account balance to check available funds before sending rewards
- check the fulfillment status of a reward order and retrieve the payout url
- list categories
- list product categories
- estimate the cost of sending a digital reward before placing the order
- payments
- product categories
- payouts
- product details
- list all countries where runa can deliver digital rewards
- supported countries
- specific reward order
- create and send a digital reward or gift card to a recipient via runa
- get account balance
- runa
- get product
- incentives
- get product denominations and redemption info
- rewards
- browse available gift cards and payout products in the runa catalog
- list all digital reward orders placed with the runa account
- browse available gift cards and payout products
- estimate cost before sending a reward
- get current account balance
- get reward order status and payout url
- estimate reward cost
- digital reward orders
- list supported countries
- browse available reward products
- b2c
- account balance
slug: rewards-distribution
source_filename: rewards-distribution.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Runa Rewards Distribution\"\n  description: >-\n    Workflow capability for digital reward and gift card distribution using\n    the Runa platform. Combines product discovery, order management, balance\n    monitoring, and cost estimation for B2C payment, employee incentive,\n    customer loyalty, and marketing reward workflows. Serves reward program\n    managers, growth engineers, and operations teams automating digital\n    reward delivery at scale.\n  tags:\n    - Gift Cards\n    - Rewards\n    - Payments\n    - Incentives\n    - Payouts\n    - B2C\n    - Loyalty\n    - Runa\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RUNA_API_KEY: RUNA_API_KEY\n\ncapability:\n  consumes:\n    - import: payouts-api\n      location: ./shared/payouts-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: rewards-distribution-api\n      description: \"Unified REST\
  \ API for Runa digital reward and gift card distribution workflows.\"\n      resources:\n        - path: /v1/catalog\n          name: catalog\n          description: \"Browse available reward products\"\n          operations:\n            - method: GET\n              name: browse-catalog\n              description: \"Browse available gift cards and payout products\"\n              call: \"payouts-api.list-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/catalog/categories\n          name: categories\n          description: \"Product categories\"\n          operations:\n            - method: GET\n              name: list-categories\n              description: \"List product categories for catalog filtering\"\n              call: \"payouts-api.list-categories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/catalog/countries\n      \
  \    name: countries\n          description: \"Supported countries\"\n          operations:\n            - method: GET\n              name: list-countries\n              description: \"List countries supported by Runa\"\n              call: \"payouts-api.list-countries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/catalog/{productId}\n          name: product\n          description: \"Product details\"\n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get product denominations and redemption info\"\n              call: \"payouts-api.get-product\"\n              with:\n                productId: \"rest.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rewards\n          name: rewards\n          description: \"Digital reward orders\"\n          operations:\n           \
  \ - method: POST\n              name: send-reward\n              description: \"Create and send a digital reward to a recipient\"\n              call: \"payouts-api.create-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-rewards\n              description: \"List all reward orders\"\n              call: \"payouts-api.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rewards/{orderId}\n          name: reward\n          description: \"Specific reward order\"\n          operations:\n            - method: GET\n              name: get-reward-status\n              description: \"Get reward order status and payout URL\"\n              call: \"payouts-api.get-order\"\n              with:\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n    \
  \              mapping: \"$.\"\n        - path: /v1/rewards/estimate\n          name: reward-estimate\n          description: \"Estimate reward cost\"\n          operations:\n            - method: POST\n              name: estimate-reward\n              description: \"Estimate cost before sending a reward\"\n              call: \"payouts-api.estimate-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/account/balance\n          name: balance\n          description: \"Account balance\"\n          operations:\n            - method: GET\n              name: get-balance\n              description: \"Get current account balance\"\n              call: \"payouts-api.get-balance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: rewards-distribution-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ digital reward and gift card distribution using Runa.\"\n      tools:\n        - name: browse-catalog\n          description: \"Browse available gift cards and payout products in the Runa catalog\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"payouts-api.list-products\"\n          with:\n            country: \"tools.country\"\n            category: \"tools.category\"\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product-details\n          description: \"Get denomination options and redemption instructions for a specific Runa product\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"payouts-api.get-product\"\n          with:\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-product-categories\n\
  \          description: \"List all product categories available in the Runa catalog (e.g., Retail, Dining, Gaming)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"payouts-api.list-categories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-supported-countries\n          description: \"List all countries where Runa can deliver digital rewards\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"payouts-api.list-countries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: estimate-reward-cost\n          description: \"Estimate the cost of sending a digital reward before placing the order\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"payouts-api.estimate-order\"\n          with:\n            payment_method: \"tools.paymentMethod\"\
  \n            items: \"tools.items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-reward\n          description: \"Create and send a digital reward or gift card to a recipient via Runa\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"payouts-api.create-order\"\n          with:\n            payment_method: \"tools.paymentMethod\"\n            items: \"tools.items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-reward-status\n          description: \"Check the fulfillment status of a reward order and retrieve the payout URL\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"payouts-api.get-order\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: list-rewards\n          description: \"List all digital reward orders placed with the Runa account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"payouts-api.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-balance\n          description: \"Get the current Runa account balance to check available funds before sending rewards\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"payouts-api.get-balance\"\n          with:\n            currency: \"tools.currency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/runa/refs/heads/main/capabilities/rewards-distribution.yaml
tags:
- Gift Cards
- Rewards
- Payments
- Incentives
- Payouts
- B2C
- Loyalty
- Runa
tools:
- description: Browse available gift cards and payout products in the Runa catalog
  hints:
    openWorld: true
    readOnly: true
  name: browse-catalog
- description: Get denomination options and redemption instructions for a specific Runa product
  hints:
    openWorld: false
    readOnly: true
  name: get-product-details
- description: List all product categories available in the Runa catalog (e.g., Retail, Dining, Gaming)
  hints:
    openWorld: false
    readOnly: true
  name: list-product-categories
- description: List all countries where Runa can deliver digital rewards
  hints:
    openWorld: false
    readOnly: true
  name: list-supported-countries
- description: Estimate the cost of sending a digital reward before placing the order
  hints:
    openWorld: false
    readOnly: true
  name: estimate-reward-cost
- description: Create and send a digital reward or gift card to a recipient via Runa
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-reward
- description: Check the fulfillment status of a reward order and retrieve the payout URL
  hints:
    openWorld: false
    readOnly: true
  name: get-reward-status
- description: List all digital reward orders placed with the Runa account
  hints:
    openWorld: false
    readOnly: true
  name: list-rewards
- description: Get the current Runa account balance to check available funds before sending rewards
  hints:
    openWorld: false
    readOnly: true
  name: get-account-balance
---
