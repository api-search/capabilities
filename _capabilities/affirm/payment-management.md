---
categories:
- payments
consumed_apis: []
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
- affirm
- dispute management.
- list all disputes.
- backend developer integrating affirm bnpl into a merchant's e-commerce checkout.
- list all transactions.
- capture transaction
- create an affirm bnpl checkout session for a customer purchase.
- get affirm promotional financing terms and messaging for a purchase amount.
- refund a captured transaction.
- authorize a transaction.
- merchant operations team member managing transaction reconciliation and dispute resolution.
- refund transaction
- refund a transaction.
- authorize transaction
- capture an authorized transaction.
- payment transaction management.
- list all affirm payment disputes for a merchant.
- capture an authorized affirm transaction to collect funds.
- transactions
- store checkout
- read checkout
- retrieve or update a checkout session.
- buy now pay later
- specific dispute operations.
- list disputes
- checkout session management.
- list all affirm payment transactions for reconciliation.
- get dispute
- create an affirm checkout session.
- initiation and management of customer financing sessions.
- read a checkout session.
- promotional messaging.
- merchant engineer
- read an affirm checkout session by token.
- disputes
- checkout
- void an authorized affirm transaction before capture.
- capture a transaction.
- get details of a specific affirm payment dispute.
- full bnpl payment lifecycle from checkout through capture, refund, and dispute management.
- payments
- handling of customer chargebacks and disputes.
- displaying financing terms and promotional messaging to customers.
- submit dispute evidence
- payment ops
- get dispute details.
- authorize an affirm transaction using a checkout token.
- submit evidence to contest an affirm payment dispute.
- void transaction
- authorization, capture, void, and refund of payment transactions.
- list transactions
- get promotional financing terms.
- refund a captured affirm transaction partially or fully.
- get promo messaging
- get promo
slug: payment-management
source_filename: payment-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Affirm Payment Management\n  description: Unified workflow capability for managing the full Affirm BNPL payment lifecycle — from initiating checkout\n    sessions through transaction authorization, capture, refund, and dispute resolution. Used by merchant engineers and payment\n    operations teams.\n  tags:\n  - Affirm\n  - Payments\n  - Buy Now Pay Later\n  - Checkout\n  - Transactions\n  - Disputes\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AFFIRM_PUBLIC_KEY: AFFIRM_PUBLIC_KEY\n    AFFIRM_PRIVATE_KEY: AFFIRM_PRIVATE_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: affirm-checkout\n    baseUri: https://api.affirm.com/api/v1\n    description: Affirm Checkout API for creating and managing BNPL checkout sessions.\n    authentication:\n      type: basic\n      username: '{{AFFIRM_PUBLIC_KEY}}'\n      password: '{{AFFIRM_PRIVATE_KEY}}'\n    resources:\n    - name: checkouts\n  \
  \    path: /checkouts\n      description: Checkout session management operations.\n      operations:\n      - name: store-checkout\n        method: POST\n        description: Create and store a new Affirm checkout session.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: direct-checkout\n        method: POST\n        description: Initiate a direct checkout flow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: checkout-by-token\n      path: /checkouts/{token}\n      description: Operations on a specific checkout by token.\n      operations:\n      - name: read-checkout\n        method: GET\n        description: Retrieve a checkout session by token.\n        inputParameters:\n        - name: token\n          in: path\n          type: string\n          required: true\n          description: The checkout token.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-checkout\n        method: POST\n        description: Update an existing checkout session.\n        inputParameters:\n        - name: token\n          in: path\n          type: string\n          required: true\n          description: The checkout token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resend-checkout\n        method: POST\n        description: Resend a checkout link via email or SMS.\n        inputParameters:\n        - name: token\n          in: path\n          type: string\n          required: true\n          description: The checkout token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: affirm-transactions\n    baseUri:\
  \ https://api.affirm.com/api/v1\n    description: Affirm Transactions API for managing payment transaction lifecycle.\n    authentication:\n      type: basic\n      username: '{{AFFIRM_PUBLIC_KEY}}'\n      password: '{{AFFIRM_PRIVATE_KEY}}'\n    resources:\n    - name: transactions\n      path: /transactions\n      description: Transaction management operations.\n      operations:\n      - name: list-transactions\n        method: GET\n        description: List all transactions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: authorize-transaction\n        method: POST\n        description: Authorize a transaction using a checkout token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transaction-by-id\n      path: /transactions/{id}\n      description: Operations on a specific transaction.\n      operations:\n\
  \      - name: read-transaction\n        method: GET\n        description: Read a transaction by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Transaction ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: capture-transaction\n        method: POST\n        description: Capture an authorized transaction.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Transaction ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refund-transaction\n        method: POST\n        description: Refund a captured transaction.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Transaction ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: void-transaction\n        method: POST\n        description: Void an authorized transaction.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Transaction ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: affirm-disputes\n    baseUri: https://api.affirm.com/api/v1\n    description: Affirm Disputes API for managing payment disputes.\n    authentication:\n      type: basic\n      username: '{{AFFIRM_PUBLIC_KEY}}'\n      password: '{{AFFIRM_PRIVATE_KEY}}'\n    resources:\n    - name: disputes\n      path: /disputes\n      description: Dispute management operations.\n      operations:\n      - name: list-disputes\n\
  \        method: GET\n        description: List all disputes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dispute-by-id\n      path: /disputes/{dispute_id}\n      description: Operations on a specific dispute.\n      operations:\n      - name: get-dispute\n        method: GET\n        description: Retrieve a dispute by ID.\n        inputParameters:\n        - name: dispute_id\n          in: path\n          type: string\n          required: true\n          description: Dispute ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: close-dispute\n        method: POST\n        description: Close a dispute.\n        inputParameters:\n        - name: dispute_id\n          in: path\n          type: string\n          required: true\n          description: Dispute ID.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: submit-dispute-evidence\n        method: POST\n        description: Submit evidence for a dispute.\n        inputParameters:\n        - name: dispute_id\n          in: path\n          type: string\n          required: true\n          description: Dispute ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: affirm-promos\n    baseUri: https://www.affirm.com/api/promos/v2\n    description: Affirm Promos API for fetching financing promotional messaging.\n    authentication:\n      type: apikey\n      key: public_api_key\n      value: '{{AFFIRM_PUBLIC_KEY}}'\n      placement: query\n    resources:\n    - name: promos\n      path: /\n      description: Get promotional messaging for a purchase amount.\n      operations:\n      - name: get-promo\n        method: GET\n        description: Get financing\
  \ terms and promotional messaging for a given purchase amount.\n        inputParameters:\n        - name: public_api_key\n          in: query\n          type: string\n          required: true\n          description: Merchant public API key.\n        - name: amount\n          in: query\n          type: integer\n          required: true\n          description: Purchase amount in cents.\n        - name: page_type\n          in: query\n          type: string\n          required: false\n          description: Page type context (product, cart, homepage).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: affirm-payment-api\n    description: Unified REST API for Affirm BNPL payment management.\n    resources:\n    - path: /v1/checkouts\n      name: checkouts\n      description: Checkout session management.\n      operations:\n      - method: POST\n        name:\
  \ store-checkout\n        description: Create an Affirm checkout session.\n        call: affirm-checkout.store-checkout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/checkouts/{token}\n      name: checkout-by-token\n      description: Retrieve or update a checkout session.\n      operations:\n      - method: GET\n        name: read-checkout\n        description: Read a checkout session.\n        call: affirm-checkout.read-checkout\n        with:\n          token: rest.token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions\n      name: transactions\n      description: Payment transaction management.\n      operations:\n      - method: GET\n        name: list-transactions\n        description: List all transactions.\n        call: affirm-transactions.list-transactions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: authorize-transaction\n\
  \        description: Authorize a transaction.\n        call: affirm-transactions.authorize-transaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions/{id}/capture\n      name: transaction-capture\n      description: Capture an authorized transaction.\n      operations:\n      - method: POST\n        name: capture-transaction\n        description: Capture a transaction.\n        call: affirm-transactions.capture-transaction\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions/{id}/refund\n      name: transaction-refund\n      description: Refund a captured transaction.\n      operations:\n      - method: POST\n        name: refund-transaction\n        description: Refund a transaction.\n        call: affirm-transactions.refund-transaction\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/disputes\n      name: disputes\n      description: Dispute management.\n      operations:\n      - method: GET\n        name: list-disputes\n        description: List all disputes.\n        call: affirm-disputes.list-disputes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/disputes/{dispute_id}\n      name: dispute-by-id\n      description: Specific dispute operations.\n      operations:\n      - method: GET\n        name: get-dispute\n        description: Get dispute details.\n        call: affirm-disputes.get-dispute\n        with:\n          dispute_id: rest.dispute_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/promos\n      name: promos\n      description: Promotional messaging.\n      operations:\n      - method: GET\n        name: get-promo\n        description: Get promotional financing terms.\n        call: affirm-promos.get-promo\n        with:\n          amount: rest.amount\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: affirm-payment-mcp\n    transport: http\n    description: MCP server for AI-assisted Affirm BNPL payment management.\n    tools:\n    - name: store-checkout\n      description: Create an Affirm BNPL checkout session for a customer purchase.\n      hints:\n        readOnly: false\n        destructive: false\n      call: affirm-checkout.store-checkout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-checkout\n      description: Read an Affirm checkout session by token.\n      hints:\n        readOnly: true\n        destructive: false\n      call: affirm-checkout.read-checkout\n      with:\n        token: tools.token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-transactions\n      description: List all Affirm payment transactions for reconciliation.\n      hints:\n        readOnly: true\n    \
  \    destructive: false\n      call: affirm-transactions.list-transactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authorize-transaction\n      description: Authorize an Affirm transaction using a checkout token.\n      hints:\n        readOnly: false\n        destructive: false\n      call: affirm-transactions.authorize-transaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: capture-transaction\n      description: Capture an authorized Affirm transaction to collect funds.\n      hints:\n        readOnly: false\n        destructive: false\n      call: affirm-transactions.capture-transaction\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refund-transaction\n      description: Refund a captured Affirm transaction partially or fully.\n      hints:\n        readOnly: false\n        destructive: true\n      call: affirm-transactions.refund-transaction\n\
  \      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: void-transaction\n      description: Void an authorized Affirm transaction before capture.\n      hints:\n        readOnly: false\n        destructive: true\n      call: affirm-transactions.void-transaction\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-disputes\n      description: List all Affirm payment disputes for a merchant.\n      hints:\n        readOnly: true\n        destructive: false\n      call: affirm-disputes.list-disputes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dispute\n      description: Get details of a specific Affirm payment dispute.\n      hints:\n        readOnly: true\n        destructive: false\n      call: affirm-disputes.get-dispute\n      with:\n        dispute_id: tools.dispute_id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: submit-dispute-evidence\n      description: Submit evidence to contest an Affirm payment dispute.\n      hints:\n        readOnly: false\n        destructive: false\n      call: affirm-disputes.submit-dispute-evidence\n      with:\n        dispute_id: tools.dispute_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-promo-messaging\n      description: Get Affirm promotional financing terms and messaging for a purchase amount.\n      hints:\n        readOnly: true\n        destructive: false\n      call: affirm-promos.get-promo\n      with:\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
