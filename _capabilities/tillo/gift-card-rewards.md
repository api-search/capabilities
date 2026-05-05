---
categories: []
consumed_apis:
- tillo-gift-cards
description: Workflow capability for delivering gift card rewards and incentives at scale using Tillo. Combines brand discovery, card issuance, balance checking, and order management into a unified rewards workflow. Designed for loyalty programs, employee rewards platforms, customer incentive tools, and promotional campaigns.
layout: capability
name: Tillo Gift Card Rewards
operations:
- description: List available gift card brands
  method: GET
  name: list-brands
  path: /v1/brands
- description: Get brand details including denominations and features
  method: GET
  name: get-brand
  path: /v1/brands/{brand_identifier}
- description: Issue a digital gift card reward
  method: POST
  name: issue-digital-card
  path: /v1/rewards/issue
- description: Order an async gift card reward
  method: POST
  name: order-digital-card
  path: /v1/rewards/order
- description: Check status of a gift card reward order
  method: GET
  name: get-order-status
  path: /v1/rewards/{client_request_id}/status
- description: Check remaining balance on a gift card
  method: POST
  name: check-balance
  path: /v1/cards/balance
- description: Check denomination availability for a brand
  method: POST
  name: check-stock
  path: /v1/cards/stock
- description: Refund a gift card order
  method: POST
  name: refund-order
  path: /v1/rewards/{client_request_id}/refund
- description: Get float account balances
  method: GET
  name: get-float-balance
  path: /v1/float
personas: []
provider_name: Tillo
provider_slug: tillo
search_terms:
- get current float account balances across all currencies
- float account management
- issue a digital gift card reward
- check status of a gift card reward order
- get order status
- issue digital card
- list available tillo gift card brands for reward selection
- list available gift card brands
- check stock
- get float balance
- finance
- get float account balances
- refund issued rewards
- check denomination availability for a brand
- denomination availability
- issue gift card rewards
- check balance
- gift cards
- loyalty
- get brand
- order async gift card rewards
- gift card balance check
- order an async gift card reward
- list brands
- refund a gift card order and return funds to float
- gift card brand catalog
- payments
- order digital card
- brand details
- incentives
- tillo
- rewards
- reward order status
- place an async gift card order for brands requiring asynchronous processing
- check denomination availability for a fixed-value gift card brand
- issue a digital gift card reward to a user
- get brand details including denominations and features
- check remaining balance on a tillo gift card
- check the status of a gift card reward order
- get gift card brand details including denominations and eligibility
- check remaining balance on a gift card
- refund order
- refund a gift card order
slug: gift-card-rewards
source_filename: gift-card-rewards.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tillo Gift Card Rewards\"\n  description: >-\n    Workflow capability for delivering gift card rewards and incentives at scale\n    using Tillo. Combines brand discovery, card issuance, balance checking, and\n    order management into a unified rewards workflow. Designed for loyalty\n    programs, employee rewards platforms, customer incentive tools, and\n    promotional campaigns.\n  tags:\n    - Tillo\n    - Gift Cards\n    - Rewards\n    - Incentives\n    - Loyalty\n    - Finance\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TILLO_API_KEY: TILLO_API_KEY\n      TILLO_API_SECRET: TILLO_API_SECRET\n\ncapability:\n  consumes:\n    - import: tillo-gift-cards\n      location: ./shared/gift-card-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tillo-rewards-api\n      description: \"Unified REST API for Tillo gift card rewards delivery.\"\n      resources:\n\
  \        - path: /v1/brands\n          name: brands\n          description: \"Gift card brand catalog\"\n          operations:\n            - method: GET\n              name: list-brands\n              description: \"List available gift card brands\"\n              call: \"tillo-gift-cards.list-brands\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/brands/{brand_identifier}\n          name: brand-detail\n          description: \"Brand details\"\n          operations:\n            - method: GET\n              name: get-brand\n              description: \"Get brand details including denominations and features\"\n              call: \"tillo-gift-cards.get-brand\"\n              with:\n                brand_identifier: \"rest.brand_identifier\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rewards/issue\n          name: reward-issue\n       \
  \   description: \"Issue gift card rewards\"\n          operations:\n            - method: POST\n              name: issue-digital-card\n              description: \"Issue a digital gift card reward\"\n              call: \"tillo-gift-cards.issue-digital-card\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rewards/order\n          name: reward-order\n          description: \"Order async gift card rewards\"\n          operations:\n            - method: POST\n              name: order-digital-card\n              description: \"Order an async gift card reward\"\n              call: \"tillo-gift-cards.order-digital-card\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rewards/{client_request_id}/status\n          name: reward-status\n          description: \"Reward order status\"\n          operations:\n            - method: GET\n            \
  \  name: get-order-status\n              description: \"Check status of a gift card reward order\"\n              call: \"tillo-gift-cards.get-order-status\"\n              with:\n                client_request_id: \"rest.client_request_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cards/balance\n          name: card-balance\n          description: \"Gift card balance check\"\n          operations:\n            - method: POST\n              name: check-balance\n              description: \"Check remaining balance on a gift card\"\n              call: \"tillo-gift-cards.check-balance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cards/stock\n          name: card-stock\n          description: \"Denomination availability\"\n          operations:\n            - method: POST\n              name: check-stock\n              description: \"\
  Check denomination availability for a brand\"\n              call: \"tillo-gift-cards.check-stock\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rewards/{client_request_id}/refund\n          name: reward-refund\n          description: \"Refund issued rewards\"\n          operations:\n            - method: POST\n              name: refund-order\n              description: \"Refund a gift card order\"\n              call: \"tillo-gift-cards.refund-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/float\n          name: float-balance\n          description: \"Float account management\"\n          operations:\n            - method: GET\n              name: get-float-balance\n              description: \"Get float account balances\"\n              call: \"tillo-gift-cards.get-float-balance\"\n              outputParameters:\n            \
  \    - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tillo-rewards-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Tillo gift card rewards delivery.\"\n      tools:\n        - name: list-brands\n          description: \"List available Tillo gift card brands for reward selection\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tillo-gift-cards.list-brands\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-brand\n          description: \"Get gift card brand details including denominations and eligibility\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tillo-gift-cards.get-brand\"\n          with:\n            brand_identifier: \"tools.brand_identifier\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: issue-digital-card\n          description: \"Issue a digital gift card reward to a user\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"tillo-gift-cards.issue-digital-card\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: order-digital-card\n          description: \"Place an async gift card order for brands requiring asynchronous processing\"\n          hints:\n            readOnly: false\n          call: \"tillo-gift-cards.order-digital-card\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-balance\n          description: \"Check remaining balance on a Tillo gift card\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tillo-gift-cards.check-balance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-stock\n\
  \          description: \"Check denomination availability for a fixed-value gift card brand\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tillo-gift-cards.check-stock\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order-status\n          description: \"Check the status of a gift card reward order\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tillo-gift-cards.get-order-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: refund-order\n          description: \"Refund a gift card order and return funds to float\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"tillo-gift-cards.refund-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-float-balance\n  \
  \        description: \"Get current float account balances across all currencies\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tillo-gift-cards.get-float-balance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tillo/refs/heads/main/capabilities/gift-card-rewards.yaml
tags:
- Tillo
- Gift Cards
- Rewards
- Incentives
- Loyalty
- Finance
tools:
- description: List available Tillo gift card brands for reward selection
  hints:
    idempotent: true
    readOnly: true
  name: list-brands
- description: Get gift card brand details including denominations and eligibility
  hints:
    idempotent: true
    readOnly: true
  name: get-brand
- description: Issue a digital gift card reward to a user
  hints:
    destructive: false
    readOnly: false
  name: issue-digital-card
- description: Place an async gift card order for brands requiring asynchronous processing
  hints:
    readOnly: false
  name: order-digital-card
- description: Check remaining balance on a Tillo gift card
  hints:
    idempotent: true
    readOnly: true
  name: check-balance
- description: Check denomination availability for a fixed-value gift card brand
  hints:
    idempotent: true
    readOnly: true
  name: check-stock
- description: Check the status of a gift card reward order
  hints:
    idempotent: true
    readOnly: true
  name: get-order-status
- description: Refund a gift card order and return funds to float
  hints:
    destructive: false
    readOnly: false
  name: refund-order
- description: Get current float account balances across all currencies
  hints:
    idempotent: true
    readOnly: true
  name: get-float-balance
---
