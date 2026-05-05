---
categories: []
consumed_apis:
- api
description: Unified workflow capability composing Zendit APIs.
layout: capability
name: Zendit Workflow
operations:
- description: Zendit Get Balance
  method: GET
  name: get-balance
  path: /v1/api
- description: Zendit List Brands
  method: GET
  name: list-brands
  path: /v1/api
- description: Zendit Get Brand
  method: GET
  name: get-brand
  path: /v1/api
- description: Zendit Get Brand Redemption Instructions
  method: GET
  name: get-brand-redemption-instructions
  path: /v1/api
- description: Zendit List Topup Offers
  method: GET
  name: list-topup-offers
  path: /v1/api
- description: Zendit Get Topup Offer
  method: GET
  name: get-topup-offer
  path: /v1/api
- description: Zendit List Topup Purchases
  method: GET
  name: list-topup-purchases
  path: /v1/api
- description: Zendit Create Topup Purchase
  method: POST
  name: create-topup-purchase
  path: /v1/api
- description: Zendit Get Topup Purchase
  method: GET
  name: get-topup-purchase
  path: /v1/api
- description: Zendit List ESIM Offers
  method: GET
  name: list-esim-offers
  path: /v1/api
- description: Zendit Get ESIM Offer
  method: GET
  name: get-esim-offer
  path: /v1/api
- description: Zendit List ESIM Purchases
  method: GET
  name: list-esim-purchases
  path: /v1/api
- description: Zendit Create ESIM Purchase
  method: POST
  name: create-esim-purchase
  path: /v1/api
- description: Zendit Get ESIM Purchase
  method: GET
  name: get-esim-purchase
  path: /v1/api
- description: Zendit Get ESIM QR Code
  method: GET
  name: get-esim-qr-code
  path: /v1/api
- description: Zendit Get ESIM Plans
  method: GET
  name: get-esim-plans
  path: /v1/api
- description: Zendit Get ESIM Refund
  method: GET
  name: get-esim-refund
  path: /v1/api
- description: Zendit Create ESIM Refund
  method: POST
  name: create-esim-refund
  path: /v1/api
- description: Zendit List Voucher Offers
  method: GET
  name: list-voucher-offers
  path: /v1/api
- description: Zendit Get Voucher Offer
  method: GET
  name: get-voucher-offer
  path: /v1/api
personas: []
provider_name: Zendit
provider_slug: zendit
search_terms:
- api list topup purchases
- mobile top-up
- api get esim purchase
- api get brand redemption instructions
- api list esim purchases
- api create esim purchase
- zendit get esim purchase
- get voucher offer
- api get esim qr code
- api list voucher offers
- list topup offers
- list voucher offers
- zendit get esim refund
- api list brands
- api create esim refund
- esim
- zendit get topup purchase
- api get balance
- list topup purchases
- get esim purchase
- get brand redemption instructions
- api list esim offers
- get esim offer
- list esim offers
- get esim plans
- zendit
- api get esim plans
- api get esim refund
- get brand
- gift cards
- zendit list topup purchases
- get balance
- list brands
- zendit list brands
- api get brand
- create esim purchase
- get esim refund
- api list topup offers
- api get esim offer
- create topup purchase
- get esim qr code
- api get topup offer
- payments
- zendit get brand
- zendit create esim purchase
- create esim refund
- zendit get brand redemption instructions
- get topup offer
- api get voucher offer
- zendit list topup offers
- operations for api
- zendit get balance
- zendit create topup purchase
- get topup purchase
- zendit get esim qr code
- api create topup purchase
- zendit get topup offer
- zendit list esim purchases
- zendit get esim plans
- zendit get voucher offer
- api get topup purchase
- zendit list voucher offers
- list esim purchases
- prepaid
- zendit get esim offer
- zendit list esim offers
- zendit create esim refund
slug: zendit-workflow
source_filename: zendit-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Zendit Workflow\n  description: Unified workflow capability composing Zendit APIs.\n  tags:\n    - Zendit\n  created: '2026-05-03'\n  modified: '2026-05-03'\ncapability:\n  consumes:\n    - import: api\n      location: ./shared/api.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: zendit-api\n      description: Unified REST API for Zendit\n      resources:\n        - path: /v1/api\n          name: api\n          description: Operations for api\n          operations:\n            - method: GET\n              name: get-balance\n              description: Zendit Get Balance\n              call: api.get-balance\n            - method: GET\n              name: list-brands\n              description: Zendit List Brands\n              call: api.list-brands\n            - method: GET\n              name: get-brand\n              description: Zendit Get Brand\n              call: api.get-brand\n            - method: GET\n  \
  \            name: get-brand-redemption-instructions\n              description: Zendit Get Brand Redemption Instructions\n              call: api.get-brand-redemption-instructions\n            - method: GET\n              name: list-topup-offers\n              description: Zendit List Topup Offers\n              call: api.list-topup-offers\n            - method: GET\n              name: get-topup-offer\n              description: Zendit Get Topup Offer\n              call: api.get-topup-offer\n            - method: GET\n              name: list-topup-purchases\n              description: Zendit List Topup Purchases\n              call: api.list-topup-purchases\n            - method: POST\n              name: create-topup-purchase\n              description: Zendit Create Topup Purchase\n              call: api.create-topup-purchase\n            - method: GET\n              name: get-topup-purchase\n              description: Zendit Get Topup Purchase\n              call: api.get-topup-purchase\n\
  \            - method: GET\n              name: list-esim-offers\n              description: Zendit List ESIM Offers\n              call: api.list-esim-offers\n            - method: GET\n              name: get-esim-offer\n              description: Zendit Get ESIM Offer\n              call: api.get-esim-offer\n            - method: GET\n              name: list-esim-purchases\n              description: Zendit List ESIM Purchases\n              call: api.list-esim-purchases\n            - method: POST\n              name: create-esim-purchase\n              description: Zendit Create ESIM Purchase\n              call: api.create-esim-purchase\n            - method: GET\n              name: get-esim-purchase\n              description: Zendit Get ESIM Purchase\n              call: api.get-esim-purchase\n            - method: GET\n              name: get-esim-qr-code\n              description: Zendit Get ESIM QR Code\n              call: api.get-esim-qr-code\n            - method: GET\n\
  \              name: get-esim-plans\n              description: Zendit Get ESIM Plans\n              call: api.get-esim-plans\n            - method: GET\n              name: get-esim-refund\n              description: Zendit Get ESIM Refund\n              call: api.get-esim-refund\n            - method: POST\n              name: create-esim-refund\n              description: Zendit Create ESIM Refund\n              call: api.create-esim-refund\n            - method: GET\n              name: list-voucher-offers\n              description: Zendit List Voucher Offers\n              call: api.list-voucher-offers\n            - method: GET\n              name: get-voucher-offer\n              description: Zendit Get Voucher Offer\n              call: api.get-voucher-offer\n    - type: mcp\n      port: 9090\n      namespace: zendit-mcp\n      transport: http\n      description: MCP server for Zendit\n      tools:\n        - name: api-get-balance\n          description: Zendit Get Balance\n \
  \         hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-balance\n        - name: api-list-brands\n          description: Zendit List Brands\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.list-brands\n        - name: api-get-brand\n          description: Zendit Get Brand\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-brand\n        - name: api-get-brand-redemption-instructions\n          description: Zendit Get Brand Redemption Instructions\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-brand-redemption-instructions\n        - name: api-list-topup-offers\n          description: Zendit List Topup Offers\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.list-topup-offers\n        - name: api-get-topup-offer\n          description: Zendit Get Topup Offer\n\
  \          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-topup-offer\n        - name: api-list-topup-purchases\n          description: Zendit List Topup Purchases\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.list-topup-purchases\n        - name: api-create-topup-purchase\n          description: Zendit Create Topup Purchase\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.create-topup-purchase\n        - name: api-get-topup-purchase\n          description: Zendit Get Topup Purchase\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-topup-purchase\n        - name: api-list-esim-offers\n          description: Zendit List ESIM Offers\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.list-esim-offers\n        - name: api-get-esim-offer\n          description:\
  \ Zendit Get ESIM Offer\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-esim-offer\n        - name: api-list-esim-purchases\n          description: Zendit List ESIM Purchases\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.list-esim-purchases\n        - name: api-create-esim-purchase\n          description: Zendit Create ESIM Purchase\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.create-esim-purchase\n        - name: api-get-esim-purchase\n          description: Zendit Get ESIM Purchase\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-esim-purchase\n        - name: api-get-esim-qr-code\n          description: Zendit Get ESIM QR Code\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-esim-qr-code\n        - name: api-get-esim-plans\n      \
  \    description: Zendit Get ESIM Plans\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-esim-plans\n        - name: api-get-esim-refund\n          description: Zendit Get ESIM Refund\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-esim-refund\n        - name: api-create-esim-refund\n          description: Zendit Create ESIM Refund\n          hints:\n            readOnly: false\n            openWorld: true\n          call: api.create-esim-refund\n        - name: api-list-voucher-offers\n          description: Zendit List Voucher Offers\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.list-voucher-offers\n        - name: api-get-voucher-offer\n          description: Zendit Get Voucher Offer\n          hints:\n            readOnly: true\n            openWorld: true\n          call: api.get-voucher-offer\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zendit/refs/heads/main/capabilities/zendit-workflow.yaml
tags:
- Zendit
tools:
- description: Zendit Get Balance
  hints:
    openWorld: true
    readOnly: true
  name: api-get-balance
- description: Zendit List Brands
  hints:
    openWorld: true
    readOnly: true
  name: api-list-brands
- description: Zendit Get Brand
  hints:
    openWorld: true
    readOnly: true
  name: api-get-brand
- description: Zendit Get Brand Redemption Instructions
  hints:
    openWorld: true
    readOnly: true
  name: api-get-brand-redemption-instructions
- description: Zendit List Topup Offers
  hints:
    openWorld: true
    readOnly: true
  name: api-list-topup-offers
- description: Zendit Get Topup Offer
  hints:
    openWorld: true
    readOnly: true
  name: api-get-topup-offer
- description: Zendit List Topup Purchases
  hints:
    openWorld: true
    readOnly: true
  name: api-list-topup-purchases
- description: Zendit Create Topup Purchase
  hints:
    openWorld: true
    readOnly: false
  name: api-create-topup-purchase
- description: Zendit Get Topup Purchase
  hints:
    openWorld: true
    readOnly: true
  name: api-get-topup-purchase
- description: Zendit List ESIM Offers
  hints:
    openWorld: true
    readOnly: true
  name: api-list-esim-offers
- description: Zendit Get ESIM Offer
  hints:
    openWorld: true
    readOnly: true
  name: api-get-esim-offer
- description: Zendit List ESIM Purchases
  hints:
    openWorld: true
    readOnly: true
  name: api-list-esim-purchases
- description: Zendit Create ESIM Purchase
  hints:
    openWorld: true
    readOnly: false
  name: api-create-esim-purchase
- description: Zendit Get ESIM Purchase
  hints:
    openWorld: true
    readOnly: true
  name: api-get-esim-purchase
- description: Zendit Get ESIM QR Code
  hints:
    openWorld: true
    readOnly: true
  name: api-get-esim-qr-code
- description: Zendit Get ESIM Plans
  hints:
    openWorld: true
    readOnly: true
  name: api-get-esim-plans
- description: Zendit Get ESIM Refund
  hints:
    openWorld: true
    readOnly: true
  name: api-get-esim-refund
- description: Zendit Create ESIM Refund
  hints:
    openWorld: true
    readOnly: false
  name: api-create-esim-refund
- description: Zendit List Voucher Offers
  hints:
    openWorld: true
    readOnly: true
  name: api-list-voucher-offers
- description: Zendit Get Voucher Offer
  hints:
    openWorld: true
    readOnly: true
  name: api-get-voucher-offer
---
