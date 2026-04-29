---
categories: []
consumed_apis:
- card-issuance
- traditional-fulfillment
- bin-lookup
- automatic-billing-updater
- payment-account-mgmt
- payment-account-ref
- account-catalog
- universal-spec
- account-validation
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
- validate account details
- submit pan-related event for account level management
- get payment account reference
- lookup bin
- account management
- card issuance and management
- fraud detection
- issue a new card
- mastercard
- automatic billing updates
- request updated card credentials for card-on-file
- credit cards
- bin lookup
- look up bin information
- submit pan event
- digital identity
- issue card
- financial services
- manage a payment account
- payment account management
- request updated card credentials
- manage a payment account lifecycle
- issuers
- get billing updates
- list bins
- create a physical card fulfillment order
- create fulfillment order
- validate account
- open banking
- payments
- manage payment account
- query payment account reference to link tokens to accounts
- manage account
- list available mastercard bins
- get account catalog
- card management
- look up bin information for a card
- issue a new mastercard card
- retrieve account catalog data
- get card details
slug: card-and-account-management
source_filename: card-and-account-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Mastercard Card and Account Management\"\n  description: \"Unified workflow for issuers and card managers to handle card issuance, fulfillment, BIN lookups, billing updates, payment account management, and account catalog services.\"\n  tags:\n    - Mastercard\n    - Card Management\n    - Account Management\n    - Issuers\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n      MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\n\ncapability:\n  consumes:\n    - import: card-issuance\n      location: ./shared/card-issuance.yaml\n    - import: traditional-fulfillment\n      location: ./shared/traditional-fulfillment.yaml\n    - import: bin-lookup\n      location: ./shared/bin-lookup.yaml\n    - import: automatic-billing-updater\n      location: ./shared/automatic-billing-updater.yaml\n    - import: payment-account-mgmt\n      location:\
  \ ./shared/payment-account-management.yaml\n    - import: payment-account-ref\n      location: ./shared/payment-account-reference.yaml\n    - import: account-catalog\n      location: ./shared/account-catalog.yaml\n    - import: universal-spec\n      location: ./shared/universal-spec-submission.yaml\n    - import: account-validation\n      location: ./shared/account-validation.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: card-account-api\n      description: \"Unified REST API for card and account management.\"\n      resources:\n        - path: /v1/cards\n          name: cards\n          description: \"Card issuance and management\"\n          operations:\n            - method: POST\n              name: issue-card\n              description: \"Issue a new card\"\n              call: \"card-issuance.issue-card\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bins\n          name: bins\n\
  \          description: \"BIN lookup\"\n          operations:\n            - method: POST\n              name: lookup-bin\n              description: \"Look up BIN information\"\n              call: \"bin-lookup.lookup-bin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/billing-updates\n          name: billing-updates\n          description: \"Automatic billing updates\"\n          operations:\n            - method: POST\n              name: get-billing-updates\n              description: \"Request updated card credentials\"\n              call: \"automatic-billing-updater.get-updates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts\n          name: accounts\n          description: \"Payment account management\"\n          operations:\n            - method: POST\n              name: manage-account\n              description: \"Manage\
  \ a payment account\"\n              call: \"payment-account-mgmt.manage-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: card-account-mcp\n      transport: http\n      description: \"MCP server for AI-assisted card and account management.\"\n      tools:\n        - name: issue-card\n          description: \"Issue a new Mastercard card\"\n          hints:\n            readOnly: false\n          call: \"card-issuance.issue-card\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-card-details\n          description: \"Get card details\"\n          hints:\n            readOnly: true\n          call: \"card-issuance.get-card\"\n          with:\n            card_id: \"tools.card_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-fulfillment-order\n     \
  \     description: \"Create a physical card fulfillment order\"\n          hints:\n            readOnly: false\n          call: \"traditional-fulfillment.create-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-bin\n          description: \"Look up BIN information for a card\"\n          hints:\n            readOnly: true\n          call: \"bin-lookup.lookup-bin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bins\n          description: \"List available Mastercard BINs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"bin-lookup.list-bins\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-billing-updates\n          description: \"Request updated card credentials for card-on-file\"\n          hints:\n            readOnly: true\n          call: \"automatic-billing-updater.get-updates\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-payment-account\n          description: \"Manage a payment account lifecycle\"\n          hints:\n            readOnly: false\n          call: \"payment-account-mgmt.manage-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-payment-account-reference\n          description: \"Query payment account reference to link tokens to accounts\"\n          hints:\n            readOnly: true\n          call: \"payment-account-ref.get-par\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-account\n          description: \"Validate account details\"\n          hints:\n            readOnly: true\n          call: \"account-validation.validate-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-catalog\n\
  \          description: \"Retrieve account catalog data\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"account-catalog.get-catalog\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-pan-event\n          description: \"Submit PAN-related event for account level management\"\n          hints:\n            readOnly: false\n          call: \"universal-spec.submit-spec\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
