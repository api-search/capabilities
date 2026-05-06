---
categories: []
consumed_apis: []
description: A complete payments solution, built for speed and simplicity. The Pin Payments API enables you to charge cards, manage customers, issue refunds, store cards, and run subscriptions.
layout: capability
name: Pin Payments API
operations:
- description: Create a charge
  method: POST
  name: post-charges
  path: /charges
- description: List charges
  method: GET
  name: get-charges
  path: /charges
- description: Search charges
  method: GET
  name: get-charges-search
  path: /charges/search
- description: Retrieve a charge
  method: GET
  name: get-charges-charge-token
  path: /charges/{charge_token}
- description: Void an authorized charge
  method: PUT
  name: put-charges-charge-token-void
  path: /charges/{charge_token}/void
- description: Capture a previously authorized charge
  method: PUT
  name: put-charges-charge-token-capture
  path: /charges/{charge_token}/capture
- description: Verify a 3D Secure result
  method: GET
  name: get-charges-verify
  path: /charges/verify
- description: List refunds for a charge
  method: GET
  name: get-charges-charge-token-refunds
  path: /charges/{charge_token}/refunds
- description: Create a refund
  method: POST
  name: post-charges-charge-token-refunds
  path: /charges/{charge_token}/refunds
- description: List refunds
  method: GET
  name: get-refunds
  path: /refunds
- description: Retrieve a refund
  method: GET
  name: get-refunds-refund-token
  path: /refunds/{refund_token}
- description: Create a customer
  method: POST
  name: post-customers
  path: /customers
- description: List customers
  method: GET
  name: get-customers
  path: /customers
- description: Retrieve a customer
  method: GET
  name: get-customers-customer-token
  path: /customers/{customer_token}
- description: Update a customer
  method: PUT
  name: put-customers-customer-token
  path: /customers/{customer_token}
- description: Delete a customer
  method: DELETE
  name: delete-customers-customer-token
  path: /customers/{customer_token}
- description: List charges for a customer
  method: GET
  name: get-customers-customer-token-charges
  path: /customers/{customer_token}/charges
- description: List cards for a customer
  method: GET
  name: get-customers-customer-token-cards
  path: /customers/{customer_token}/cards
- description: Add a card to a customer
  method: POST
  name: post-customers-customer-token-cards
  path: /customers/{customer_token}/cards
- description: Remove a non-primary card from a customer
  method: DELETE
  name: delete-customers-customer-token-cards-card-token
  path: /customers/{customer_token}/cards/{card_token}
- description: List subscriptions for a customer
  method: GET
  name: get-customers-customer-token-subscriptions
  path: /customers/{customer_token}/subscriptions
- description: Cancel a customer subscription
  method: DELETE
  name: delete-customers-customer-token-subscriptions-su
  path: /customers/{customer_token}/subscriptions/{sub_token}
- description: Tokenize a card
  method: POST
  name: post-cards
  path: /cards
- description: Retrieve a card
  method: GET
  name: get-cards-card-token
  path: /cards/{card_token}
personas: []
provider_name: Pin Payments
provider_slug: pin-payments
search_terms:
- add a card to a customer
- verify a 3d secure result
- post customers
- get customers customer token charges
- post cards
- delete customers customer token
- get charges charge token refunds
- post customers customer token cards
- retrieve a card
- create a refund
- put customers customer token
- get charges
- post charges
- get customers customer token cards
- cancel a customer subscription
- delete a customer
- list cards for a customer
- delete customers customer token subscriptions su
- get customers customer token subscriptions
- tokenize a card
- list subscriptions for a customer
- get customers customer token
- create a charge
- capture a previously authorized charge
- list refunds
- pin
- cards
- get charges verify
- get refunds refund token
- put charges charge token void
- get charges search
- retrieve a refund
- search charges
- list refunds for a charge
- remove a non-primary card from a customer
- refunds
- get cards card token
- api
- retrieve a customer
- payments
- create a customer
- list customers
- list charges for a customer
- subscriptions
- update a customer
- put charges charge token capture
- get customers
- get refunds
- delete customers customer token cards card token
- get charges charge token
- retrieve a charge
- void an authorized charge
- list charges
- post charges charge token refunds
slug: pin-payments-capability
source_filename: pin-payments-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pin Payments API\n  description: A complete payments solution, built for speed and simplicity. The Pin Payments API enables you to charge cards,\n    manage customers, issue refunds, store cards, and run subscriptions.\n  tags:\n  - Pin\n  - Payments\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pin-payments\n    baseUri: https://api.pinpayments.com/1\n    description: Pin Payments API HTTP API.\n    authentication:\n      type: basic\n      username: '{{PIN_PAYMENTS_USERNAME}}'\n      password: '{{PIN_PAYMENTS_PASSWORD}}'\n    resources:\n    - name: charges\n      path: /charges\n      operations:\n      - name: post-charges\n        method: POST\n        description: Create a charge\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-charges\n        method: GET\n     \
  \   description: List charges\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charges-search\n      path: /charges/search\n      operations:\n      - name: get-charges-search\n        method: GET\n        description: Search charges\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n        - name: start_date\n          in: query\n          type: string\n        - name: end_date\n          in: query\n          type: string\n        - name: sort\n          in: query\n          type: string\n        - name: direction\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charges-charge-token\n      path: /charges/{charge_token}\n      operations:\n      - name: get-charges-charge-token\n        method: GET\n        description:\
  \ Retrieve a charge\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charges-charge-token-void\n      path: /charges/{charge_token}/void\n      operations:\n      - name: put-charges-charge-token-void\n        method: PUT\n        description: Void an authorized charge\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charges-charge-token-capture\n      path: /charges/{charge_token}/capture\n      operations:\n      - name: put-charges-charge-token-capture\n        method: PUT\n        description: Capture a previously authorized charge\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charges-verify\n      path: /charges/verify\n      operations:\n      - name: get-charges-verify\n        method: GET\n        description:\
  \ Verify a 3D Secure result\n        inputParameters:\n        - name: session_token\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charges-charge-token-refunds\n      path: /charges/{charge_token}/refunds\n      operations:\n      - name: get-charges-charge-token-refunds\n        method: GET\n        description: List refunds for a charge\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-charges-charge-token-refunds\n        method: POST\n        description: Create a refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refunds\n      path: /refunds\n      operations:\n      - name: get-refunds\n        method: GET\n        description:\
  \ List refunds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refunds-refund-token\n      path: /refunds/{refund_token}\n      operations:\n      - name: get-refunds-refund-token\n        method: GET\n        description: Retrieve a refund\n        inputParameters:\n        - name: refund_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /customers\n      operations:\n      - name: post-customers\n        method: POST\n        description: Create a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-customers\n        method: GET\n        description: List customers\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: customers-customer-token\n      path: /customers/{customer_token}\n      operations:\n      - name: get-customers-customer-token\n        method: GET\n        description: Retrieve a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-customers-customer-token\n        method: PUT\n        description: Update a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-customers-customer-token\n        method: DELETE\n        description: Delete a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-customer-token-charges\n      path: /customers/{customer_token}/charges\n      operations:\n      - name:\
  \ get-customers-customer-token-charges\n        method: GET\n        description: List charges for a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-customer-token-cards\n      path: /customers/{customer_token}/cards\n      operations:\n      - name: get-customers-customer-token-cards\n        method: GET\n        description: List cards for a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-customers-customer-token-cards\n        method: POST\n        description: Add a card to a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-customer-token-cards-card-token\n      path: /customers/{customer_token}/cards/{card_token}\n      operations:\n      - name: delete-customers-customer-token-cards-card-token\n\
  \        method: DELETE\n        description: Remove a non-primary card from a customer\n        inputParameters:\n        - name: card_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-customer-token-subscriptions\n      path: /customers/{customer_token}/subscriptions\n      operations:\n      - name: get-customers-customer-token-subscriptions\n        method: GET\n        description: List subscriptions for a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers-customer-token-subscriptions-sub-token\n      path: /customers/{customer_token}/subscriptions/{sub_token}\n      operations:\n      - name: delete-customers-customer-token-subscriptions-su\n        method: DELETE\n        description: Cancel a customer\
  \ subscription\n        inputParameters:\n        - name: sub_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cards\n      path: /cards\n      operations:\n      - name: post-cards\n        method: POST\n        description: Tokenize a card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cards-card-token\n      path: /cards/{card_token}\n      operations:\n      - name: get-cards-card-token\n        method: GET\n        description: Retrieve a card\n        inputParameters:\n        - name: card_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port:\
  \ 8080\n    namespace: pin-payments-rest\n    description: REST adapter for Pin Payments API.\n    resources:\n    - path: /charges\n      name: post-charges\n      operations:\n      - method: POST\n        name: post-charges\n        description: Create a charge\n        call: pin-payments.post-charges\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charges\n      name: get-charges\n      operations:\n      - method: GET\n        name: get-charges\n        description: List charges\n        call: pin-payments.get-charges\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charges/search\n      name: get-charges-search\n      operations:\n      - method: GET\n        name: get-charges-search\n        description: Search charges\n        call: pin-payments.get-charges-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charges/{charge_token}\n      name: get-charges-charge-token\n\
  \      operations:\n      - method: GET\n        name: get-charges-charge-token\n        description: Retrieve a charge\n        call: pin-payments.get-charges-charge-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charges/{charge_token}/void\n      name: put-charges-charge-token-void\n      operations:\n      - method: PUT\n        name: put-charges-charge-token-void\n        description: Void an authorized charge\n        call: pin-payments.put-charges-charge-token-void\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charges/{charge_token}/capture\n      name: put-charges-charge-token-capture\n      operations:\n      - method: PUT\n        name: put-charges-charge-token-capture\n        description: Capture a previously authorized charge\n        call: pin-payments.put-charges-charge-token-capture\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charges/verify\n\
  \      name: get-charges-verify\n      operations:\n      - method: GET\n        name: get-charges-verify\n        description: Verify a 3D Secure result\n        call: pin-payments.get-charges-verify\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charges/{charge_token}/refunds\n      name: get-charges-charge-token-refunds\n      operations:\n      - method: GET\n        name: get-charges-charge-token-refunds\n        description: List refunds for a charge\n        call: pin-payments.get-charges-charge-token-refunds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charges/{charge_token}/refunds\n      name: post-charges-charge-token-refunds\n      operations:\n      - method: POST\n        name: post-charges-charge-token-refunds\n        description: Create a refund\n        call: pin-payments.post-charges-charge-token-refunds\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /refunds\n      name: get-refunds\n      operations:\n      - method: GET\n        name: get-refunds\n        description: List refunds\n        call: pin-payments.get-refunds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /refunds/{refund_token}\n      name: get-refunds-refund-token\n      operations:\n      - method: GET\n        name: get-refunds-refund-token\n        description: Retrieve a refund\n        call: pin-payments.get-refunds-refund-token\n        with:\n          refund_token: rest.refund_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers\n      name: post-customers\n      operations:\n      - method: POST\n        name: post-customers\n        description: Create a customer\n        call: pin-payments.post-customers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers\n      name: get-customers\n      operations:\n      - method:\
  \ GET\n        name: get-customers\n        description: List customers\n        call: pin-payments.get-customers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customer_token}\n      name: get-customers-customer-token\n      operations:\n      - method: GET\n        name: get-customers-customer-token\n        description: Retrieve a customer\n        call: pin-payments.get-customers-customer-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customer_token}\n      name: put-customers-customer-token\n      operations:\n      - method: PUT\n        name: put-customers-customer-token\n        description: Update a customer\n        call: pin-payments.put-customers-customer-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customer_token}\n      name: delete-customers-customer-token\n      operations:\n      - method: DELETE\n   \
  \     name: delete-customers-customer-token\n        description: Delete a customer\n        call: pin-payments.delete-customers-customer-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customer_token}/charges\n      name: get-customers-customer-token-charges\n      operations:\n      - method: GET\n        name: get-customers-customer-token-charges\n        description: List charges for a customer\n        call: pin-payments.get-customers-customer-token-charges\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customer_token}/cards\n      name: get-customers-customer-token-cards\n      operations:\n      - method: GET\n        name: get-customers-customer-token-cards\n        description: List cards for a customer\n        call: pin-payments.get-customers-customer-token-cards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customer_token}/cards\n\
  \      name: post-customers-customer-token-cards\n      operations:\n      - method: POST\n        name: post-customers-customer-token-cards\n        description: Add a card to a customer\n        call: pin-payments.post-customers-customer-token-cards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customer_token}/cards/{card_token}\n      name: delete-customers-customer-token-cards-card-token\n      operations:\n      - method: DELETE\n        name: delete-customers-customer-token-cards-card-token\n        description: Remove a non-primary card from a customer\n        call: pin-payments.delete-customers-customer-token-cards-card-token\n        with:\n          card_token: rest.card_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customer_token}/subscriptions\n      name: get-customers-customer-token-subscriptions\n      operations:\n      - method: GET\n        name: get-customers-customer-token-subscriptions\n\
  \        description: List subscriptions for a customer\n        call: pin-payments.get-customers-customer-token-subscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customers/{customer_token}/subscriptions/{sub_token}\n      name: delete-customers-customer-token-subscriptions-su\n      operations:\n      - method: DELETE\n        name: delete-customers-customer-token-subscriptions-su\n        description: Cancel a customer subscription\n        call: pin-payments.delete-customers-customer-token-subscriptions-su\n        with:\n          sub_token: rest.sub_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cards\n      name: post-cards\n      operations:\n      - method: POST\n        name: post-cards\n        description: Tokenize a card\n        call: pin-payments.post-cards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cards/{card_token}\n      name:\
  \ get-cards-card-token\n      operations:\n      - method: GET\n        name: get-cards-card-token\n        description: Retrieve a card\n        call: pin-payments.get-cards-card-token\n        with:\n          card_token: rest.card_token\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pin-payments-mcp\n    transport: http\n    description: MCP adapter for Pin Payments API for AI agent use.\n    tools:\n    - name: post-charges\n      description: Create a charge\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pin-payments.post-charges\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-charges\n      description: List charges\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pin-payments.get-charges\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: get-charges-search\n      description: Search charges\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pin-payments.get-charges-search\n      with:\n        query: tools.query\n        start_date: tools.start_date\n        end_date: tools.end_date\n        sort: tools.sort\n        direction: tools.direction\n      inputParameters:\n      - name: query\n        type: string\n        description: query\n      - name: start_date\n        type: string\n        description: start_date\n      - name: end_date\n        type: string\n        description: end_date\n      - name: sort\n        type: string\n        description: sort\n      - name: direction\n        type: integer\n        description: direction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-charges-charge-token\n      description: Retrieve a charge\n      hints:\n        readOnly: true\n        destructive: false\n       \
  \ idempotent: true\n      call: pin-payments.get-charges-charge-token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-charges-charge-token-void\n      description: Void an authorized charge\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: pin-payments.put-charges-charge-token-void\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-charges-charge-token-capture\n      description: Capture a previously authorized charge\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: pin-payments.put-charges-charge-token-capture\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-charges-verify\n      description: Verify a 3D Secure result\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pin-payments.get-charges-verify\n      with:\n \
  \       session_token: tools.session_token\n      inputParameters:\n      - name: session_token\n        type: string\n        description: session_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-charges-charge-token-refunds\n      description: List refunds for a charge\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pin-payments.get-charges-charge-token-refunds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-charges-charge-token-refunds\n      description: Create a refund\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pin-payments.post-charges-charge-token-refunds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-refunds\n      description: List refunds\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: pin-payments.get-refunds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-refunds-refund-token\n      description: Retrieve a refund\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pin-payments.get-refunds-refund-token\n      with:\n        refund_token: tools.refund_token\n      inputParameters:\n      - name: refund_token\n        type: string\n        description: refund_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-customers\n      description: Create a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pin-payments.post-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customers\n      description: List customers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: pin-payments.get-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customers-customer-token\n      description: Retrieve a customer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pin-payments.get-customers-customer-token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-customers-customer-token\n      description: Update a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: pin-payments.put-customers-customer-token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-customers-customer-token\n      description: Delete a customer\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pin-payments.delete-customers-customer-token\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-customers-customer-token-charges\n      description: List charges for a customer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pin-payments.get-customers-customer-token-charges\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customers-customer-token-cards\n      description: List cards for a customer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pin-payments.get-customers-customer-token-cards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-customers-customer-token-cards\n      description: Add a card to a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pin-payments.post-customers-customer-token-cards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-customers-customer-token-cards-card-token\n\
  \      description: Remove a non-primary card from a customer\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pin-payments.delete-customers-customer-token-cards-card-token\n      with:\n        card_token: tools.card_token\n      inputParameters:\n      - name: card_token\n        type: string\n        description: card_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customers-customer-token-subscriptions\n      description: List subscriptions for a customer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pin-payments.get-customers-customer-token-subscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-customers-customer-token-subscriptions-su\n      description: Cancel a customer subscription\n      hints:\n        readOnly: false\n        destructive: true\n   \
  \     idempotent: true\n      call: pin-payments.delete-customers-customer-token-subscriptions-su\n      with:\n        sub_token: tools.sub_token\n      inputParameters:\n      - name: sub_token\n        type: string\n        description: sub_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-cards\n      description: Tokenize a card\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pin-payments.post-cards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cards-card-token\n      description: Retrieve a card\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pin-payments.get-cards-card-token\n      with:\n        card_token: tools.card_token\n      inputParameters:\n      - name: card_token\n        type: string\n        description: card_token\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PIN_PAYMENTS_USERNAME: PIN_PAYMENTS_USERNAME\n    PIN_PAYMENTS_PASSWORD: PIN_PAYMENTS_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pin-payments/refs/heads/main/capabilities/pin-payments-capability.yaml
tags:
- Pin
- Payments
- API
tools:
- description: Create a charge
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-charges
- description: List charges
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-charges
- description: Search charges
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-charges-search
- description: Retrieve a charge
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-charges-charge-token
- description: Void an authorized charge
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-charges-charge-token-void
- description: Capture a previously authorized charge
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-charges-charge-token-capture
- description: Verify a 3D Secure result
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-charges-verify
- description: List refunds for a charge
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-charges-charge-token-refunds
- description: Create a refund
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-charges-charge-token-refunds
- description: List refunds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-refunds
- description: Retrieve a refund
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-refunds-refund-token
- description: Create a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-customers
- description: List customers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-customers
- description: Retrieve a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-customers-customer-token
- description: Update a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-customers-customer-token
- description: Delete a customer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-customers-customer-token
- description: List charges for a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-customers-customer-token-charges
- description: List cards for a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-customers-customer-token-cards
- description: Add a card to a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-customers-customer-token-cards
- description: Remove a non-primary card from a customer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-customers-customer-token-cards-card-token
- description: List subscriptions for a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-customers-customer-token-subscriptions
- description: Cancel a customer subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-customers-customer-token-subscriptions-su
- description: Tokenize a card
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cards
- description: Retrieve a card
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cards-card-token
---
