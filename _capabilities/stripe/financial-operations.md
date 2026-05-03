---
categories: []
consumed_apis:
- stripe-payouts
- stripe-refunds
- stripe-disputes
description: Unified capability for financial operations and treasury workflows. Combines Stripe Payouts, Refunds, Disputes, and Balance APIs to support payout management, refund processing, chargeback handling, and balance monitoring. Used by finance teams and payment operations engineers.
layout: capability
name: Stripe Financial Operations
operations:
- description: List payouts
  method: GET
  name: list-payouts
  path: /v1/payouts
- description: Create a payout
  method: POST
  name: create-payout
  path: /v1/payouts
- description: Get a payout
  method: GET
  name: get-payout
  path: /v1/payouts/{payout}
- description: List refunds
  method: GET
  name: list-refunds
  path: /v1/refunds
- description: Create a refund
  method: POST
  name: create-refund
  path: /v1/refunds
- description: List disputes
  method: GET
  name: list-disputes
  path: /v1/disputes
- description: Get a dispute
  method: GET
  name: get-dispute
  path: /v1/disputes/{dispute}
personas: []
provider_name: Stripe
provider_slug: stripe
search_terms:
- create a payout
- t1
- create refund
- financial operations
- dispute management
- stripe
- individual dispute
- list stripe payouts to bank accounts
- reverse a completed stripe payout
- get refund
- get payout
- get a payout
- update dispute
- financial services
- reverse payout
- submit evidence for a stripe dispute to contest a chargeback
- list payouts
- get a dispute
- issue a refund on a stripe charge
- refunds
- payments
- list disputes
- payout management
- list refunds
- create a refund
- commerce
- individual payout
- create payout
- list stripe disputes (chargebacks)
- refund management
- disputes
- treasury
- payouts
- create a stripe payout to a bank account
- retrieve a stripe payout by id
- get dispute
- list stripe refunds
- fintech
- retrieve a stripe refund by id
- cancel payout
- cancel a pending stripe payout
- get details of a stripe dispute
slug: financial-operations
source_filename: financial-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stripe Financial Operations\"\n  description: >-\n    Unified capability for financial operations and treasury workflows. Combines Stripe Payouts,\n    Refunds, Disputes, and Balance APIs to support payout management, refund processing, chargeback\n    handling, and balance monitoring. Used by finance teams and payment operations engineers.\n  tags:\n    - Stripe\n    - Payouts\n    - Refunds\n    - Disputes\n    - Financial Operations\n    - Treasury\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STRIPE_API_KEY: STRIPE_API_KEY\n\ncapability:\n  consumes:\n    - import: stripe-payouts\n      location: ./shared/payouts.yaml\n    - import: stripe-refunds\n      location: ./shared/refunds.yaml\n    - import: stripe-disputes\n      location: ./shared/disputes.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: stripe-financial-ops-api\n      description: \"\
  Unified REST API for Stripe financial operations.\"\n      resources:\n        - path: /v1/payouts\n          name: payouts\n          description: \"Payout management\"\n          operations:\n            - method: GET\n              name: list-payouts\n              description: \"List payouts\"\n              call: \"stripe-payouts.list-payouts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-payout\n              description: \"Create a payout\"\n              call: \"stripe-payouts.create-payout\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payouts/{payout}\n          name: payout\n          description: \"Individual payout\"\n          operations:\n            - method: GET\n              name: get-payout\n              description: \"Get a payout\"\n              call: \"stripe-payouts.get-payout\"\
  \n              with:\n                payout: \"rest.payout\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/refunds\n          name: refunds\n          description: \"Refund management\"\n          operations:\n            - method: GET\n              name: list-refunds\n              description: \"List refunds\"\n              call: \"stripe-refunds.list-refunds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-refund\n              description: \"Create a refund\"\n              call: \"stripe-refunds.create-refund\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disputes\n          name: disputes\n          description: \"Dispute management\"\n          operations:\n            - method: GET\n              name: list-disputes\n\
  \              description: \"List disputes\"\n              call: \"stripe-disputes.list-disputes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disputes/{dispute}\n          name: dispute\n          description: \"Individual dispute\"\n          operations:\n            - method: GET\n              name: get-dispute\n              description: \"Get a dispute\"\n              call: \"stripe-disputes.get-dispute\"\n              with:\n                dispute: \"rest.dispute\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: stripe-financial-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Stripe financial operations.\"\n      tools:\n        - name: list-payouts\n          description: \"List Stripe payouts to bank accounts\"\n          hints:\n            readOnly: true\n \
  \         call: \"stripe-payouts.list-payouts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-payout\n          description: \"Create a Stripe payout to a bank account\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-payouts.create-payout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-payout\n          description: \"Retrieve a Stripe payout by ID\"\n          hints:\n            readOnly: true\n          call: \"stripe-payouts.get-payout\"\n          with:\n            payout: \"tools.payout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-payout\n          description: \"Cancel a pending Stripe payout\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"stripe-payouts.cancel-payout\"\n    \
  \      with:\n            payout: \"tools.payout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reverse-payout\n          description: \"Reverse a completed Stripe payout\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"stripe-payouts.reverse-payout\"\n          with:\n            payout: \"tools.payout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-refunds\n          description: \"List Stripe refunds\"\n          hints:\n            readOnly: true\n          call: \"stripe-refunds.list-refunds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-refund\n          description: \"Issue a refund on a Stripe charge\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-refunds.create-refund\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-refund\n          description: \"Retrieve a Stripe refund by ID\"\n          hints:\n            readOnly: true\n          call: \"stripe-refunds.get-refund\"\n          with:\n            refund: \"tools.refund\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-disputes\n          description: \"List Stripe disputes (chargebacks)\"\n          hints:\n            readOnly: true\n          call: \"stripe-disputes.list-disputes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dispute\n          description: \"Get details of a Stripe dispute\"\n          hints:\n            readOnly: true\n          call: \"stripe-disputes.get-dispute\"\n          with:\n            dispute: \"tools.dispute\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: update-dispute\n          description: \"Submit evidence for a Stripe dispute to contest a chargeback\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-disputes.update-dispute\"\n          with:\n            dispute: \"tools.dispute\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stripe/refs/heads/main/capabilities/financial-operations.yaml
tags:
- Stripe
- Payouts
- Refunds
- Disputes
- Financial Operations
- Treasury
tools:
- description: List Stripe payouts to bank accounts
  hints:
    readOnly: true
  name: list-payouts
- description: Create a Stripe payout to a bank account
  hints:
    destructive: false
    readOnly: false
  name: create-payout
- description: Retrieve a Stripe payout by ID
  hints:
    readOnly: true
  name: get-payout
- description: Cancel a pending Stripe payout
  hints:
    destructive: true
    readOnly: false
  name: cancel-payout
- description: Reverse a completed Stripe payout
  hints:
    destructive: true
    readOnly: false
  name: reverse-payout
- description: List Stripe refunds
  hints:
    readOnly: true
  name: list-refunds
- description: Issue a refund on a Stripe charge
  hints:
    destructive: false
    readOnly: false
  name: create-refund
- description: Retrieve a Stripe refund by ID
  hints:
    readOnly: true
  name: get-refund
- description: List Stripe disputes (chargebacks)
  hints:
    readOnly: true
  name: list-disputes
- description: Get details of a Stripe dispute
  hints:
    readOnly: true
  name: get-dispute
- description: Submit evidence for a Stripe dispute to contest a chargeback
  hints:
    destructive: false
    readOnly: false
  name: update-dispute
---
