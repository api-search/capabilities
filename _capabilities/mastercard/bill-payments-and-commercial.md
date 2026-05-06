---
categories: []
consumed_apis: []
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
- fraud detection
- get commercial notifications
- create a virtual card
- validate a bill payment before processing
- financial services
- search for billers in the rpps network
- search billers
- business spending controls
- treasury
- create a business spending control rule
- create a virtual card for commercial payments
- credit cards
- biller management
- validate a bill payment
- list business spending control rules
- commercial
- digital identity
- open banking
- business payments
- create a spending control rule
- bill payment validation
- mastercard
- validate payment
- create spending control
- payments
- list spending controls
- retrieve commercial event notifications
- create virtual card
- bill payments
- get biller details
- validate bill payment
- search for billers
slug: bill-payments-and-commercial
source_filename: bill-payments-and-commercial.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Bill Payments and Commercial\n  description: Unified workflow for treasury teams and accounts payable to manage bill payments, business payment controls,\n    virtual cards, commercial event notifications, and installment plans.\n  tags:\n  - Mastercard\n  - Bill Payments\n  - Commercial\n  - Treasury\n  - Business Payments\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: bill-pay\n    baseUri: https://api.mastercard.com/bill-pay\n    description: Mastercard Bill Pay API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: billers\n      path: /billers\n      description: Biller management\n      operations:\n    \
  \  - name: search-billers\n        method: POST\n        description: Search for billers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            search: '{{tools.search}}'\n      - name: get-biller\n        method: GET\n        description: Get biller details\n        inputParameters:\n        - name: biller_id\n          in: path\n          type: string\n          required: true\n          description: Biller identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: bill-payment-validator\n    baseUri: https://api.mastercard.com/bill-payment-validator\n    description: Mastercard Bill Payment Validator API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n\
  \    resources:\n    - name: validations\n      path: /validations\n      description: Bill payment validation\n      operations:\n      - name: validate-payment\n        method: POST\n        description: Validate a bill payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payment: '{{tools.payment}}'\n  - type: http\n    namespace: business-payment-controls\n    baseUri: https://api.mastercard.com/business-payment-controls\n    description: Mastercard Business Payment Controls API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: controls\n      path: /controls\n      description: Payment control management\n      operations:\n      - name: create-control\n        method: POST\n        description: Create a spending control\
  \ rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            control: '{{tools.control}}'\n      - name: list-controls\n        method: GET\n        description: List spending control rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: in-control-commercial\n    baseUri: https://api.mastercard.com/in-control/commercial\n    description: Mastercard In Control for Commercial Payments API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: virtual-cards\n      path: /virtual-cards\n      description: Virtual card management\n      operations:\n      - name: create-virtual-card\n        method: POST\n        description: Create\
  \ a virtual card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            card: '{{tools.card}}'\n  - type: http\n    namespace: commercial-notifications\n    baseUri: https://api.mastercard.com/commercial/notifications\n    description: Mastercard Commercial Event Notifications API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: notifications\n      path: /notifications\n      description: Event notification management\n      operations:\n      - name: get-notifications\n        method: GET\n        description: Retrieve commercial event notifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8087\n    namespace:\
  \ bill-commercial-api\n    description: Unified REST API for bill payments and commercial payment workflows.\n    resources:\n    - path: /v1/billers\n      name: billers\n      description: Biller management\n      operations:\n      - method: POST\n        name: search-billers\n        description: Search for billers\n        call: bill-pay.search-billers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payment-validations\n      name: payment-validations\n      description: Bill payment validation\n      operations:\n      - method: POST\n        name: validate-payment\n        description: Validate a bill payment\n        call: bill-payment-validator.validate-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spending-controls\n      name: spending-controls\n      description: Business spending controls\n      operations:\n      - method: POST\n        name: create-spending-control\n        description:\
  \ Create a spending control rule\n        call: business-payment-controls.create-control\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/virtual-cards\n      name: virtual-cards\n      description: Virtual card management\n      operations:\n      - method: POST\n        name: create-virtual-card\n        description: Create a virtual card\n        call: in-control-commercial.create-virtual-card\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9097\n    namespace: bill-commercial-mcp\n    transport: http\n    description: MCP server for AI-assisted bill payment and commercial operations.\n    tools:\n    - name: search-billers\n      description: Search for billers in the RPPS network\n      hints:\n        readOnly: true\n      call: bill-pay.search-billers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-biller-details\n      description: Get biller details\n\
  \      hints:\n        readOnly: true\n      call: bill-pay.get-biller\n      with:\n        biller_id: tools.biller_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-bill-payment\n      description: Validate a bill payment before processing\n      hints:\n        readOnly: true\n      call: bill-payment-validator.validate-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-spending-control\n      description: Create a business spending control rule\n      hints:\n        readOnly: false\n      call: business-payment-controls.create-control\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-spending-controls\n      description: List business spending control rules\n      hints:\n        readOnly: true\n      call: business-payment-controls.list-controls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-virtual-card\n      description:\
  \ Create a virtual card for commercial payments\n      hints:\n        readOnly: false\n      call: in-control-commercial.create-virtual-card\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commercial-notifications\n      description: Retrieve commercial event notifications\n      hints:\n        readOnly: true\n      call: commercial-notifications.get-notifications\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
