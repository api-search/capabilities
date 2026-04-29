---
categories:
- payments
consumed_apis:
- affirm-checkout
- affirm-transactions
- affirm-disputes
- affirm-promos
description: Unified workflow capability for managing the full Affirm BNPL payment lifecycle — from initiating checkout sessions through transaction authorization, capture, refund, and dispute resolution. Used by merchant engineers and payment operations teams.
layout: capability
name: Affirm Payment Management
operations:
- description: Create an Affirm checkout session.
  method: POST
  name: store-checkout
  path: /v1/checkouts
- description: Read a checkout session.
  method: GET
  name: read-checkout
  path: /v1/checkouts/{token}
- description: List all transactions.
  method: GET
  name: list-transactions
  path: /v1/transactions
- description: Authorize a transaction.
  method: POST
  name: authorize-transaction
  path: /v1/transactions
- description: Capture a transaction.
  method: POST
  name: capture-transaction
  path: /v1/transactions/{id}/capture
- description: Refund a transaction.
  method: POST
  name: refund-transaction
  path: /v1/transactions/{id}/refund
- description: List all disputes.
  method: GET
  name: list-disputes
  path: /v1/disputes
- description: Get dispute details.
  method: GET
  name: get-dispute
  path: /v1/disputes/{dispute_id}
- description: Get promotional financing terms.
  method: GET
  name: get-promo
  path: /v1/promos
personas:
- description: Backend developer integrating Affirm BNPL into a merchant's e-commerce checkout.
  id: merchant-engineer
  name: Merchant Engineer
- description: Merchant operations team member managing transaction reconciliation and dispute resolution.
  id: payment-ops
  name: Payment Operations
provider_name: affirm
provider_slug: affirm
search_terms:
- transactions
- displaying financing terms and promotional messaging to customers.
- initiation and management of customer financing sessions.
- refund a captured transaction.
- backend developer integrating affirm bnpl into a merchant's e-commerce checkout.
- full bnpl payment lifecycle from checkout through capture, refund, and dispute management.
- merchant engineer
- get promo messaging
- get details of a specific affirm payment dispute.
- capture a transaction.
- list all affirm payment disputes for a merchant.
- buy now pay later
- read an affirm checkout session by token.
- payment transaction management.
- list all affirm payment transactions for reconciliation.
- get affirm promotional financing terms and messaging for a purchase amount.
- list disputes
- capture transaction
- promotional messaging.
- get promo
- create an affirm bnpl checkout session for a customer purchase.
- create an affirm checkout session.
- specific dispute operations.
- read checkout
- submit evidence to contest an affirm payment dispute.
- authorize transaction
- disputes
- authorize an affirm transaction using a checkout token.
- refund a transaction.
- authorize a transaction.
- affirm
- capture an authorized transaction.
- list all disputes.
- capture an authorized affirm transaction to collect funds.
- handling of customer chargebacks and disputes.
- payment ops
- retrieve or update a checkout session.
- refund a captured affirm transaction partially or fully.
- void an authorized affirm transaction before capture.
- refund transaction
- store checkout
- read a checkout session.
- get dispute details.
- submit dispute evidence
- merchant operations team member managing transaction reconciliation and dispute resolution.
- checkout
- payments
- void transaction
- list transactions
- get promotional financing terms.
- authorization, capture, void, and refund of payment transactions.
- dispute management.
- get dispute
- checkout session management.
- list all transactions.
slug: payment-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Affirm Payment Management\"\n  description: \"Unified workflow capability for managing the full Affirm BNPL payment lifecycle — from initiating checkout sessions through transaction authorization, capture, refund, and dispute resolution. Used by merchant engineers and payment operations teams.\"\n  tags:\n    - Affirm\n    - Payments\n    - Buy Now Pay Later\n    - Checkout\n    - Transactions\n    - Disputes\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AFFIRM_PUBLIC_KEY: AFFIRM_PUBLIC_KEY\n      AFFIRM_PRIVATE_KEY: AFFIRM_PRIVATE_KEY\n\ncapability:\n  consumes:\n    - import: affirm-checkout\n      location: ./shared/checkout.yaml\n    - import: affirm-transactions\n      location: ./shared/transactions.yaml\n    - import: affirm-disputes\n      location: ./shared/disputes.yaml\n    - import: affirm-promos\n      location: ./shared/promos.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8080\n      namespace: affirm-payment-api\n      description: \"Unified REST API for Affirm BNPL payment management.\"\n      resources:\n        - path: /v1/checkouts\n          name: checkouts\n          description: \"Checkout session management.\"\n          operations:\n            - method: POST\n              name: store-checkout\n              description: \"Create an Affirm checkout session.\"\n              call: \"affirm-checkout.store-checkout\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/checkouts/{token}\n          name: checkout-by-token\n          description: \"Retrieve or update a checkout session.\"\n          operations:\n            - method: GET\n              name: read-checkout\n              description: \"Read a checkout session.\"\n              call: \"affirm-checkout.read-checkout\"\n              with:\n                token: \"rest.token\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transactions\n          name: transactions\n          description: \"Payment transaction management.\"\n          operations:\n            - method: GET\n              name: list-transactions\n              description: \"List all transactions.\"\n              call: \"affirm-transactions.list-transactions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: authorize-transaction\n              description: \"Authorize a transaction.\"\n              call: \"affirm-transactions.authorize-transaction\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transactions/{id}/capture\n          name: transaction-capture\n          description: \"Capture an authorized transaction.\"\n          operations:\n            - method: POST\n       \
  \       name: capture-transaction\n              description: \"Capture a transaction.\"\n              call: \"affirm-transactions.capture-transaction\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transactions/{id}/refund\n          name: transaction-refund\n          description: \"Refund a captured transaction.\"\n          operations:\n            - method: POST\n              name: refund-transaction\n              description: \"Refund a transaction.\"\n              call: \"affirm-transactions.refund-transaction\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disputes\n          name: disputes\n          description: \"Dispute management.\"\n          operations:\n            - method: GET\n              name: list-disputes\n\
  \              description: \"List all disputes.\"\n              call: \"affirm-disputes.list-disputes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disputes/{dispute_id}\n          name: dispute-by-id\n          description: \"Specific dispute operations.\"\n          operations:\n            - method: GET\n              name: get-dispute\n              description: \"Get dispute details.\"\n              call: \"affirm-disputes.get-dispute\"\n              with:\n                dispute_id: \"rest.dispute_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/promos\n          name: promos\n          description: \"Promotional messaging.\"\n          operations:\n            - method: GET\n              name: get-promo\n              description: \"Get promotional financing terms.\"\n              call: \"affirm-promos.get-promo\"\n    \
  \          with:\n                amount: \"rest.amount\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: affirm-payment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Affirm BNPL payment management.\"\n      tools:\n        - name: store-checkout\n          description: \"Create an Affirm BNPL checkout session for a customer purchase.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"affirm-checkout.store-checkout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: read-checkout\n          description: \"Read an Affirm checkout session by token.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"affirm-checkout.read-checkout\"\n          with:\n            token: \"tools.token\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-transactions\n          description: \"List all Affirm payment transactions for reconciliation.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"affirm-transactions.list-transactions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: authorize-transaction\n          description: \"Authorize an Affirm transaction using a checkout token.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"affirm-transactions.authorize-transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: capture-transaction\n          description: \"Capture an authorized Affirm transaction to collect funds.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"affirm-transactions.capture-transaction\"\
  \n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: refund-transaction\n          description: \"Refund a captured Affirm transaction partially or fully.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"affirm-transactions.refund-transaction\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: void-transaction\n          description: \"Void an authorized Affirm transaction before capture.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"affirm-transactions.void-transaction\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-disputes\n          description: \"List all Affirm payment disputes\
  \ for a merchant.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"affirm-disputes.list-disputes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dispute\n          description: \"Get details of a specific Affirm payment dispute.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"affirm-disputes.get-dispute\"\n          with:\n            dispute_id: \"tools.dispute_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-dispute-evidence\n          description: \"Submit evidence to contest an Affirm payment dispute.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"affirm-disputes.submit-dispute-evidence\"\n          with:\n            dispute_id: \"tools.dispute_id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-promo-messaging\n          description: \"Get Affirm promotional financing terms and messaging for a purchase amount.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"affirm-promos.get-promo\"\n          with:\n            amount: \"tools.amount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/affirm/refs/heads/main/capabilities/payment-management.yaml
tags:
- Affirm
- Payments
- Buy Now Pay Later
- Checkout
- Transactions
- Disputes
tools:
- description: Create an Affirm BNPL checkout session for a customer purchase.
  hints:
    destructive: false
    readOnly: false
  name: store-checkout
- description: Read an Affirm checkout session by token.
  hints:
    destructive: false
    readOnly: true
  name: read-checkout
- description: List all Affirm payment transactions for reconciliation.
  hints:
    destructive: false
    readOnly: true
  name: list-transactions
- description: Authorize an Affirm transaction using a checkout token.
  hints:
    destructive: false
    readOnly: false
  name: authorize-transaction
- description: Capture an authorized Affirm transaction to collect funds.
  hints:
    destructive: false
    readOnly: false
  name: capture-transaction
- description: Refund a captured Affirm transaction partially or fully.
  hints:
    destructive: true
    readOnly: false
  name: refund-transaction
- description: Void an authorized Affirm transaction before capture.
  hints:
    destructive: true
    readOnly: false
  name: void-transaction
- description: List all Affirm payment disputes for a merchant.
  hints:
    destructive: false
    readOnly: true
  name: list-disputes
- description: Get details of a specific Affirm payment dispute.
  hints:
    destructive: false
    readOnly: true
  name: get-dispute
- description: Submit evidence to contest an Affirm payment dispute.
  hints:
    destructive: false
    readOnly: false
  name: submit-dispute-evidence
- description: Get Affirm promotional financing terms and messaging for a purchase amount.
  hints:
    destructive: false
    readOnly: true
  name: get-promo-messaging
---
