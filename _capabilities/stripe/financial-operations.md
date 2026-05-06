---
categories: []
consumed_apis: []
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
- reverse a completed stripe payout
- cancel a pending stripe payout
- get refund
- create a refund
- get payout
- submit evidence for a stripe dispute to contest a chargeback
- get details of a stripe dispute
- list payouts
- stripe
- financial operations
- financial services
- payouts
- retrieve a stripe payout by id
- create a payout
- dispute management
- list refunds
- update dispute
- refund management
- get a payout
- list stripe disputes (chargebacks)
- treasury
- retrieve a stripe refund by id
- list disputes
- commerce
- list stripe payouts to bank accounts
- create payout
- individual payout
- get dispute
- create refund
- t1
- refunds
- create a stripe payout to a bank account
- payout management
- disputes
- cancel payout
- individual dispute
- issue a refund on a stripe charge
- reverse payout
- payments
- get a dispute
- list stripe refunds
- fintech
slug: financial-operations
source_filename: financial-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stripe Financial Operations\n  description: Unified capability for financial operations and treasury workflows. Combines Stripe Payouts, Refunds, Disputes,\n    and Balance APIs to support payout management, refund processing, chargeback handling, and balance monitoring. Used by\n    finance teams and payment operations engineers.\n  tags:\n  - Stripe\n  - Payouts\n  - Refunds\n  - Disputes\n  - Financial Operations\n  - Treasury\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STRIPE_API_KEY: STRIPE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stripe-payouts\n    baseUri: https://api.stripe.com\n    description: Stripe Payouts API for managing bank transfers.\n    authentication:\n      type: bearer\n      token: '{{STRIPE_API_KEY}}'\n    resources:\n    - name: payouts\n      path: /v1/payouts\n      description: Payout collection\n      operations:\n      - name: list-payouts\n\
  \        method: GET\n        description: List all payouts\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status (pending, paid, failed, canceled)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payout\n        method: POST\n        description: Create a payout to bank account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n    - name: payout\n      path: /v1/payouts/{payout}\n      description: Individual payout\n      operations:\n\
  \      - name: get-payout\n        method: GET\n        description: Retrieve a payout by ID\n        inputParameters:\n        - name: payout\n          in: path\n          type: string\n          required: true\n          description: Payout ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payout-cancel\n      path: /v1/payouts/{payout}/cancel\n      description: Cancel a payout\n      operations:\n      - name: cancel-payout\n        method: POST\n        description: Cancel a pending payout\n        inputParameters:\n        - name: payout\n          in: path\n          type: string\n          required: true\n          description: Payout ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payout-reverse\n      path: /v1/payouts/{payout}/reverse\n      description: Reverse a payout\n      operations:\n\
  \      - name: reverse-payout\n        method: POST\n        description: Reverse a payout that has already been sent\n        inputParameters:\n        - name: payout\n          in: path\n          type: string\n          required: true\n          description: Payout ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: stripe-refunds\n    baseUri: https://api.stripe.com\n    description: Stripe Refunds API for managing charge reversals.\n    authentication:\n      type: bearer\n      token: '{{STRIPE_API_KEY}}'\n    resources:\n    - name: refunds\n      path: /v1/refunds\n      description: Refund collection\n      operations:\n      - name: list-refunds\n        method: GET\n        description: List all refunds\n        inputParameters:\n        - name: charge\n          in: query\n          type: string\n          required: false\n          description: Filter by charge ID\n\
  \        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-refund\n        method: POST\n        description: Create a refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            charge: '{{tools.charge}}'\n            amount: '{{tools.amount}}'\n    - name: refund\n      path: /v1/refunds/{refund}\n      description: Individual refund\n      operations:\n      - name: get-refund\n        method: GET\n        description: Retrieve a refund by ID\n        inputParameters:\n        - name: refund\n          in: path\n          type: string\n          required: true\n          description: Refund ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refund-cancel\n      path: /v1/refunds/{refund}/cancel\n      description: Cancel a refund\n      operations:\n      - name: cancel-refund\n        method: POST\n        description: Cancel a pending refund\n        inputParameters:\n        - name: refund\n          in: path\n          type: string\n          required: true\n          description: Refund ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: stripe-disputes\n    baseUri: https://api.stripe.com\n    description: Stripe Disputes API for managing chargebacks.\n    authentication:\n      type: bearer\n      token: '{{STRIPE_API_KEY}}'\n    resources:\n    - name: disputes\n      path: /v1/disputes\n      description: Dispute collection\n      operations:\n      - name: list-disputes\n        method: GET\n\
  \        description: List all disputes\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        - name: charge\n          in: query\n          type: string\n          required: false\n          description: Filter by charge ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dispute\n      path: /v1/disputes/{dispute}\n      description: Individual dispute\n      operations:\n      - name: get-dispute\n        method: GET\n        description: Retrieve a dispute by ID\n        inputParameters:\n        - name: dispute\n          in: path\n          type: string\n          required: true\n          description: Dispute ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dispute\n  \
  \      method: POST\n        description: Update dispute evidence\n        inputParameters:\n        - name: dispute\n          in: path\n          type: string\n          required: true\n          description: Dispute ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dispute-close\n      path: /v1/disputes/{dispute}/close\n      description: Close a dispute\n      operations:\n      - name: close-dispute\n        method: POST\n        description: Close a dispute by accepting the chargeback\n        inputParameters:\n        - name: dispute\n          in: path\n          type: string\n          required: true\n          description: Dispute ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: stripe-financial-ops-api\n    description: Unified REST API for Stripe\
  \ financial operations.\n    resources:\n    - path: /v1/payouts\n      name: payouts\n      description: Payout management\n      operations:\n      - method: GET\n        name: list-payouts\n        description: List payouts\n        call: stripe-payouts.list-payouts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-payout\n        description: Create a payout\n        call: stripe-payouts.create-payout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payouts/{payout}\n      name: payout\n      description: Individual payout\n      operations:\n      - method: GET\n        name: get-payout\n        description: Get a payout\n        call: stripe-payouts.get-payout\n        with:\n          payout: rest.payout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/refunds\n      name: refunds\n      description: Refund management\n      operations:\n\
  \      - method: GET\n        name: list-refunds\n        description: List refunds\n        call: stripe-refunds.list-refunds\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-refund\n        description: Create a refund\n        call: stripe-refunds.create-refund\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/disputes\n      name: disputes\n      description: Dispute management\n      operations:\n      - method: GET\n        name: list-disputes\n        description: List disputes\n        call: stripe-disputes.list-disputes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/disputes/{dispute}\n      name: dispute\n      description: Individual dispute\n      operations:\n      - method: GET\n        name: get-dispute\n        description: Get a dispute\n        call: stripe-disputes.get-dispute\n        with:\n          dispute: rest.dispute\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: stripe-financial-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted Stripe financial operations.\n    tools:\n    - name: list-payouts\n      description: List Stripe payouts to bank accounts\n      hints:\n        readOnly: true\n      call: stripe-payouts.list-payouts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-payout\n      description: Create a Stripe payout to a bank account\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-payouts.create-payout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-payout\n      description: Retrieve a Stripe payout by ID\n      hints:\n        readOnly: true\n      call: stripe-payouts.get-payout\n      with:\n        payout: tools.payout\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: cancel-payout\n      description: Cancel a pending Stripe payout\n      hints:\n        readOnly: false\n        destructive: true\n      call: stripe-payouts.cancel-payout\n      with:\n        payout: tools.payout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reverse-payout\n      description: Reverse a completed Stripe payout\n      hints:\n        readOnly: false\n        destructive: true\n      call: stripe-payouts.reverse-payout\n      with:\n        payout: tools.payout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-refunds\n      description: List Stripe refunds\n      hints:\n        readOnly: true\n      call: stripe-refunds.list-refunds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-refund\n      description: Issue a refund on a Stripe charge\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-refunds.create-refund\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-refund\n      description: Retrieve a Stripe refund by ID\n      hints:\n        readOnly: true\n      call: stripe-refunds.get-refund\n      with:\n        refund: tools.refund\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-disputes\n      description: List Stripe disputes (chargebacks)\n      hints:\n        readOnly: true\n      call: stripe-disputes.list-disputes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dispute\n      description: Get details of a Stripe dispute\n      hints:\n        readOnly: true\n      call: stripe-disputes.get-dispute\n      with:\n        dispute: tools.dispute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-dispute\n      description: Submit evidence for a Stripe dispute to contest a chargeback\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n      call: stripe-disputes.update-dispute\n      with:\n        dispute: tools.dispute\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
