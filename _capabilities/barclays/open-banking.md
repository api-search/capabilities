---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Open Banking
operations: []
personas: []
provider_name: Barclays
provider_slug: barclays
search_terms:
- uk banking
- open banking
- payments
- finance
- psd2
- banking
- credit cards
slug: open-banking
source_yaml: "name: Barclays Open Banking\ndescription: >-\n  Naftiko capability for Barclays Open Banking APIs covering account information,\n  payment initiation, confirmation of funds, and event notifications compliant with\n  UK Open Banking and EU PSD2 standards.\nversion: '1.0'\nprovider: Barclays\ncategory: Open Banking\ntags:\n  - Open Banking\n  - PSD2\n  - Banking\n  - Payments\n  - Account Information\nhumanURL: https://developer.barclays.com/\nactions:\n  - name: Get Account Information\n    description: Retrieve account balance, details, and metadata for an authorized customer account.\n    inputs:\n      - name: accountId\n        type: string\n        required: true\n      - name: accessToken\n        type: string\n        required: true\n    outputs:\n      - name: account\n        type: Account\n  - name: Get Transactions\n    description: Retrieve transaction history for a customer account within a date range.\n    inputs:\n      - name: accountId\n        type: string\n\
  \        required: true\n      - name: fromDate\n        type: string\n        format: date\n        required: false\n      - name: toDate\n        type: string\n        format: date\n        required: false\n      - name: accessToken\n        type: string\n        required: true\n    outputs:\n      - name: transactions\n        type: array\n        items: Transaction\n  - name: Initiate Payment\n    description: Initiate a payment from a customer's Barclays account via Open Banking.\n    inputs:\n      - name: paymentRequest\n        type: PaymentRequest\n        required: true\n      - name: accessToken\n        type: string\n        required: true\n    outputs:\n      - name: paymentConsent\n        type: PaymentConsent\n  - name: Confirm Funds\n    description: Check whether a customer account has sufficient funds for a given payment amount.\n    inputs:\n      - name: accountId\n        type: string\n        required: true\n      - name: amount\n        type: number\n        required:\
  \ true\n      - name: currency\n        type: string\n        required: true\n      - name: accessToken\n        type: string\n        required: true\n    outputs:\n      - name: fundsAvailable\n        type: boolean\n  - name: Register Client\n    description: Dynamically register a TPP client application with Barclays Open Banking.\n    inputs:\n      - name: registrationRequest\n        type: RegistrationRequest\n        required: true\n    outputs:\n      - name: clientId\n        type: string\n      - name: clientSecret\n        type: string\n  - name: Subscribe to Events\n    description: Subscribe to account and transaction event notifications via webhook.\n    inputs:\n      - name: callbackUrl\n        type: string\n        format: uri\n        required: true\n      - name: eventTypes\n        type: array\n        items: string\n        required: true\n    outputs:\n      - name: subscriptionId\n        type: string\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/barclays/refs/heads/main/capabilities/open-banking.yaml
tags: []
tools: []
---
