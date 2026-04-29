---
categories: []
consumed_apis:
- bill-pay
- bill-payment-validator
- business-payment-controls
- in-control-commercial
- commercial-notifications
description: Unified workflow for treasury teams and accounts payable to manage bill payments, business payment controls, virtual cards, commercial event notifications, and installment plans.
layout: capability
name: Mastercard Bill Payments and Commercial
operations:
- description: Search for billers
  method: POST
  name: search-billers
  path: /v1/billers
- description: Validate a bill payment
  method: POST
  name: validate-payment
  path: /v1/payment-validations
- description: Create a spending control rule
  method: POST
  name: create-spending-control
  path: /v1/spending-controls
- description: Create a virtual card
  method: POST
  name: create-virtual-card
  path: /v1/virtual-cards
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- virtual card management
- list spending controls
- biller management
- digital identity
- list business spending control rules
- payments
- open banking
- search billers
- validate payment
- commercial
- create spending control
- retrieve commercial event notifications
- business spending controls
- create virtual card
- fraud detection
- validate a bill payment before processing
- create a business spending control rule
- create a virtual card for commercial payments
- credit cards
- bill payment validation
- business payments
- treasury
- validate a bill payment
- get commercial notifications
- financial services
- get biller details
- mastercard
- bill payments
- validate bill payment
- search for billers in the rpps network
- create a spending control rule
- search for billers
- create a virtual card
slug: bill-payments-and-commercial
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Mastercard Bill Payments and Commercial\"\n  description: \"Unified workflow for treasury teams and accounts payable to manage bill payments, business payment controls, virtual cards, commercial event notifications, and installment plans.\"\n  tags:\n    - Mastercard\n    - Bill Payments\n    - Commercial\n    - Treasury\n    - Business Payments\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n      MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\n\ncapability:\n  consumes:\n    - import: bill-pay\n      location: ./shared/bill-pay.yaml\n    - import: bill-payment-validator\n      location: ./shared/bill-payment-validator.yaml\n    - import: business-payment-controls\n      location: ./shared/business-payment-controls.yaml\n    - import: in-control-commercial\n      location: ./shared/in-control-commercial.yaml\n    - import:\
  \ commercial-notifications\n      location: ./shared/commercial-event-notifications.yaml\n\n  exposes:\n    - type: rest\n      port: 8087\n      namespace: bill-commercial-api\n      description: \"Unified REST API for bill payments and commercial payment workflows.\"\n      resources:\n        - path: /v1/billers\n          name: billers\n          description: \"Biller management\"\n          operations:\n            - method: POST\n              name: search-billers\n              description: \"Search for billers\"\n              call: \"bill-pay.search-billers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payment-validations\n          name: payment-validations\n          description: \"Bill payment validation\"\n          operations:\n            - method: POST\n              name: validate-payment\n              description: \"Validate a bill payment\"\n              call: \"bill-payment-validator.validate-payment\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/spending-controls\n          name: spending-controls\n          description: \"Business spending controls\"\n          operations:\n            - method: POST\n              name: create-spending-control\n              description: \"Create a spending control rule\"\n              call: \"business-payment-controls.create-control\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/virtual-cards\n          name: virtual-cards\n          description: \"Virtual card management\"\n          operations:\n            - method: POST\n              name: create-virtual-card\n              description: \"Create a virtual card\"\n              call: \"in-control-commercial.create-virtual-card\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type:\
  \ mcp\n      port: 9097\n      namespace: bill-commercial-mcp\n      transport: http\n      description: \"MCP server for AI-assisted bill payment and commercial operations.\"\n      tools:\n        - name: search-billers\n          description: \"Search for billers in the RPPS network\"\n          hints:\n            readOnly: true\n          call: \"bill-pay.search-billers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-biller-details\n          description: \"Get biller details\"\n          hints:\n            readOnly: true\n          call: \"bill-pay.get-biller\"\n          with:\n            biller_id: \"tools.biller_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-bill-payment\n          description: \"Validate a bill payment before processing\"\n          hints:\n            readOnly: true\n          call: \"bill-payment-validator.validate-payment\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-spending-control\n          description: \"Create a business spending control rule\"\n          hints:\n            readOnly: false\n          call: \"business-payment-controls.create-control\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-spending-controls\n          description: \"List business spending control rules\"\n          hints:\n            readOnly: true\n          call: \"business-payment-controls.list-controls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-virtual-card\n          description: \"Create a virtual card for commercial payments\"\n          hints:\n            readOnly: false\n          call: \"in-control-commercial.create-virtual-card\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: get-commercial-notifications\n          description: \"Retrieve commercial event notifications\"\n          hints:\n            readOnly: true\n          call: \"commercial-notifications.get-notifications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/bill-payments-and-commercial.yaml
tags:
- Mastercard
- Bill Payments
- Commercial
- Treasury
- Business Payments
tools:
- description: Search for billers in the RPPS network
  hints:
    readOnly: true
  name: search-billers
- description: Get biller details
  hints:
    readOnly: true
  name: get-biller-details
- description: Validate a bill payment before processing
  hints:
    readOnly: true
  name: validate-bill-payment
- description: Create a business spending control rule
  hints:
    readOnly: false
  name: create-spending-control
- description: List business spending control rules
  hints:
    readOnly: true
  name: list-spending-controls
- description: Create a virtual card for commercial payments
  hints:
    readOnly: false
  name: create-virtual-card
- description: Retrieve commercial event notifications
  hints:
    readOnly: true
  name: get-commercial-notifications
---
