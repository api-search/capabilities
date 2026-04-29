---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Bancomat Payment Capability
operations: []
personas: []
provider_name: Bancomat
provider_slug: bancomat
search_terms:
- atm
- financial services
- banking
- payments
- italy
- debit cards
- mobile payments
slug: bancomat-payment-capability
source_filename: bancomat-payment-capability.yaml
source_heading: Capability Spec
source_yaml: "name: BANCOMAT Payment Capability\ndescription: >-\n  Naftiko capability for BANCOMAT Pay payment acceptance covering online checkout via QR code\n  and P2P transfers for Italian consumers and merchants.\nversion: '1.0'\nprovider: bancomat\n\nworkflows:\n  - name: Online Payment Acceptance\n    description: Merchant-initiated BANCOMAT Pay payment via QR code for e-commerce.\n    apis:\n      - bancomat:bancomat-pay\n    tools:\n      - name: CreatePayment\n        description: Initiate a BANCOMAT Pay payment transaction for a merchant.\n      - name: GenerateQRCode\n        description: Generate a QR code for customer to scan and pay.\n      - name: GetPaymentStatus\n        description: Check the current status of a payment transaction.\n      - name: RefundPayment\n        description: Process a refund for a completed BANCOMAT Pay transaction.\n    persona: PSP Developer\n\n  - name: P2P Transfer\n    description: Consumer-to-consumer bank account transfer via BANCOMAT Pay\
  \ app.\n    apis:\n      - bancomat:bancomat-pay\n    tools:\n      - name: InitiateTransfer\n        description: Start a P2P transfer to another BANCOMAT Pay user.\n      - name: ConfirmTransfer\n        description: Authorize the transfer via mobile app authentication.\n    persona: Italian Consumer\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bancomat/refs/heads/main/capabilities/bancomat-payment-capability.yaml
tags: []
tools: []
---
