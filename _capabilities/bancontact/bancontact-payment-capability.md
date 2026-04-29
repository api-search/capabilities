---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Bancontact Payment Capability
operations: []
personas: []
provider_name: Bancontact
provider_slug: bancontact
search_terms:
- e-commerce
- fintech
- banking
- debit cards
- belgium
- payments
slug: bancontact-payment-capability
source_filename: bancontact-payment-capability.yaml
source_heading: Capability Spec
source_yaml: "name: Bancontact Payment Capability\ndescription: >-\n  Naftiko capability for Bancontact Pro payment acceptance covering online checkout,\n  QR code payments, mobile app payments, and refund processing for Belgian merchants.\nversion: '1.0'\nprovider: bancontact\n\nworkflows:\n  - name: Online Checkout Payment\n    description: REST API flow for Bancontact payment acceptance in e-commerce checkout.\n    apis:\n      - bancontact:payconiq-acceptance-api\n    tools:\n      - name: CreatePayment\n        description: Create a Bancontact payment transaction.\n      - name: GetPaymentStatus\n        description: Retrieve current status of a Bancontact payment.\n      - name: CancelPayment\n        description: Cancel a pending payment transaction.\n    persona: Merchant Developer\n\n  - name: QR Code Payment\n    description: Generate and display a Bancontact QR code for in-store or invoice payment.\n    apis:\n      - bancontact:payconiq-acceptance-api\n    tools:\n      - name:\
  \ GenerateQRCode\n        description: Generate a QR code for Bancontact payment checkout.\n      - name: GetPaymentStatus\n        description: Poll or receive callback for QR code scan and payment completion.\n    persona: Merchant Developer\n\n  - name: Refund Processing\n    description: Process refunds for completed Bancontact payments.\n    apis:\n      - bancontact:payconiq-acceptance-api\n    tools:\n      - name: CreateRefund\n        description: Initiate a full or partial refund for a completed Bancontact payment.\n      - name: GetRefundStatus\n        description: Retrieve the status of a submitted refund.\n    persona: Merchant Developer\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bancontact/refs/heads/main/capabilities/bancontact-payment-capability.yaml
tags: []
tools: []
---
