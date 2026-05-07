---
categories: []
consumed_apis: []
description: Unified workflow for issuers and card managers to handle card issuance, fulfillment, BIN lookups, billing updates, payment account management, and account catalog services.
layout: capability
name: Mastercard Card and Account Management
operations:
- description: Issue a new card
  method: POST
  name: issue-card
  path: /v1/cards
- description: Look up BIN information
  method: POST
  name: lookup-bin
  path: /v1/bins
- description: Request updated card credentials
  method: POST
  name: get-billing-updates
  path: /v1/billing-updates
- description: Manage a payment account
  method: POST
  name: manage-account
  path: /v1/accounts
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- list bins
- automatic billing updates
- list available mastercard bins
- request updated card credentials
- fraud detection
- issuers
- account management
- issue a new mastercard card
- manage a payment account lifecycle
- create a physical card fulfillment order
- look up bin information for a card
- lookup bin
- manage account
- validate account details
- card management
- get card details
- create fulfillment order
- bin lookup
- validate account
- get account catalog
- financial services
- credit cards
- payment account management
- request updated card credentials for card-on-file
- submit pan-related event for account level management
- issue card
- get payment account reference
- card issuance and management
- get billing updates
- retrieve account catalog data
- issue a new card
- manage payment account
- open banking
- query payment account reference to link tokens to accounts
- submit pan event
- payments
- manage a payment account
- look up bin information
- digital identity
- mastercard
slug: card-and-account-management
source_filename: card-and-account-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Card and Account Management\n  description: Unified workflow for issuers and card managers to handle card issuance, fulfillment, BIN lookups, billing updates,\n    payment account management, and account catalog services.\n  tags:\n  - Mastercard\n  - Card Management\n  - Account Management\n  - Issuers\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: card-issuance\n    baseUri: https://api.mastercard.com/card-issuance\n    description: Mastercard Card Issuance API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: cards\n      path: /cards\n      description: Card issuance operations\n      operations:\n      -\
  \ name: issue-card\n        method: POST\n        description: Issue a new card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            card: '{{tools.card}}'\n      - name: get-card\n        method: GET\n        description: Get card details\n        inputParameters:\n        - name: card_id\n          in: path\n          type: string\n          required: true\n          description: Card identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: traditional-fulfillment\n    baseUri: https://api.mastercard.com/fulfillment\n    description: Mastercard Traditional Fulfillment Service API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n\
  \    - name: orders\n      path: /orders\n      description: Card fulfillment orders\n      operations:\n      - name: create-order\n        method: POST\n        description: Create a card fulfillment order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            order: '{{tools.order}}'\n  - type: http\n    namespace: bin-lookup\n    baseUri: https://api.mastercard.com/bin-lookup\n    description: Mastercard BIN Lookup API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: bins\n      path: /bins\n      description: BIN lookup operations\n      operations:\n      - name: lookup-bin\n        method: POST\n        description: Look up BIN information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n        body:\n          type: json\n          data:\n            bin: '{{tools.bin}}'\n      - name: list-bins\n        method: GET\n        description: List available Mastercard BINs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: automatic-billing-updater\n    baseUri: https://api.mastercard.com/automatic-billing-updater\n    description: Mastercard Automatic Billing Updater API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: updates\n      path: /updates\n      description: Card update operations\n      operations:\n      - name: get-updates\n        method: POST\n        description: Request updated card credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            request: '{{tools.request}}'\n  - type: http\n    namespace: payment-account-mgmt\n    baseUri: https://api.mastercard.com/payment-account-management\n    description: Mastercard Payment Account Management API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      description: Payment account management\n      operations:\n      - name: manage-account\n        method: POST\n        description: Manage a payment account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account: '{{tools.account}}'\n  - type: http\n    namespace: payment-account-ref\n    baseUri: https://api.mastercard.com/par\n    description:\
  \ Mastercard Payment Account Reference Inquiry API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: references\n      path: /references\n      description: PAR inquiry operations\n      operations:\n      - name: get-par\n        method: POST\n        description: Query payment account reference\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account: '{{tools.account}}'\n  - type: http\n    namespace: account-catalog\n    baseUri: https://api.mastercard.com/account-catalog\n    description: Mastercard Account Catalog Services API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: catalog\n      path: /catalog\n\
  \      description: Account catalog operations\n      operations:\n      - name: get-catalog\n        method: GET\n        description: Retrieve account catalog\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: universal-spec\n    baseUri: https://api.mastercard.com/universal-spec\n    description: Mastercard Universal Specification Submission API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: submissions\n      path: /submissions\n      description: Specification submissions\n      operations:\n      - name: submit-spec\n        method: POST\n        description: Submit PAN-related event specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            submission: '{{tools.submission}}'\n  - type: http\n    namespace: account-validation\n    baseUri: https://api.mastercard.com/account-validation\n    description: Mastercard Account Validation API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: validations\n      path: /validations\n      description: Account validation operations\n      operations:\n      - name: validate-account\n        method: POST\n        description: Validate an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account: '{{tools.account}}'\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: card-account-api\n    description: Unified REST API for card and account management.\n    resources:\n    - path: /v1/cards\n\
  \      name: cards\n      description: Card issuance and management\n      operations:\n      - method: POST\n        name: issue-card\n        description: Issue a new card\n        call: card-issuance.issue-card\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bins\n      name: bins\n      description: BIN lookup\n      operations:\n      - method: POST\n        name: lookup-bin\n        description: Look up BIN information\n        call: bin-lookup.lookup-bin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing-updates\n      name: billing-updates\n      description: Automatic billing updates\n      operations:\n      - method: POST\n        name: get-billing-updates\n        description: Request updated card credentials\n        call: automatic-billing-updater.get-updates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n \
  \     description: Payment account management\n      operations:\n      - method: POST\n        name: manage-account\n        description: Manage a payment account\n        call: payment-account-mgmt.manage-account\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: card-account-mcp\n    transport: http\n    description: MCP server for AI-assisted card and account management.\n    tools:\n    - name: issue-card\n      description: Issue a new Mastercard card\n      hints:\n        readOnly: false\n      call: card-issuance.issue-card\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-card-details\n      description: Get card details\n      hints:\n        readOnly: true\n      call: card-issuance.get-card\n      with:\n        card_id: tools.card_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-fulfillment-order\n      description: Create a physical\
  \ card fulfillment order\n      hints:\n        readOnly: false\n      call: traditional-fulfillment.create-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-bin\n      description: Look up BIN information for a card\n      hints:\n        readOnly: true\n      call: bin-lookup.lookup-bin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bins\n      description: List available Mastercard BINs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: bin-lookup.list-bins\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-billing-updates\n      description: Request updated card credentials for card-on-file\n      hints:\n        readOnly: true\n      call: automatic-billing-updater.get-updates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: manage-payment-account\n      description: Manage a payment account lifecycle\n     \
  \ hints:\n        readOnly: false\n      call: payment-account-mgmt.manage-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-payment-account-reference\n      description: Query payment account reference to link tokens to accounts\n      hints:\n        readOnly: true\n      call: payment-account-ref.get-par\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-account\n      description: Validate account details\n      hints:\n        readOnly: true\n      call: account-validation.validate-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-catalog\n      description: Retrieve account catalog data\n      hints:\n        readOnly: true\n        idempotent: true\n      call: account-catalog.get-catalog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-pan-event\n      description: Submit PAN-related event for account level management\n\
  \      hints:\n        readOnly: false\n      call: universal-spec.submit-spec\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/card-and-account-management.yaml
tags:
- Mastercard
- Card Management
- Account Management
- Issuers
tools:
- description: Issue a new Mastercard card
  hints:
    readOnly: false
  name: issue-card
- description: Get card details
  hints:
    readOnly: true
  name: get-card-details
- description: Create a physical card fulfillment order
  hints:
    readOnly: false
  name: create-fulfillment-order
- description: Look up BIN information for a card
  hints:
    readOnly: true
  name: lookup-bin
- description: List available Mastercard BINs
  hints:
    idempotent: true
    readOnly: true
  name: list-bins
- description: Request updated card credentials for card-on-file
  hints:
    readOnly: true
  name: get-billing-updates
- description: Manage a payment account lifecycle
  hints:
    readOnly: false
  name: manage-payment-account
- description: Query payment account reference to link tokens to accounts
  hints:
    readOnly: true
  name: get-payment-account-reference
- description: Validate account details
  hints:
    readOnly: true
  name: validate-account
- description: Retrieve account catalog data
  hints:
    idempotent: true
    readOnly: true
  name: get-account-catalog
- description: Submit PAN-related event for account level management
  hints:
    readOnly: false
  name: submit-pan-event
---
