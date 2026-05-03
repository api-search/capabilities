---
categories: []
consumed_apis:
- usb-accounts
- usb-rtp
description: Unified treasury management capability composing US Bank Corporate Account Information and RTP Real-Time Payments APIs. Used by corporate treasury teams, ERP systems, and financial operations for account visibility, payment reconciliation, and real-time payment origination.
layout: capability
name: US Bank Treasury Management
operations:
- description: List all corporate deposit accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Get current day balances for accounts
  method: GET
  name: get-current-balances
  path: /v1/balances/current
- description: Get previous day balances for accounts
  method: GET
  name: get-previous-balances
  path: /v1/balances/previous
- description: Get account transaction history by date range
  method: GET
  name: get-transactions
  path: /v1/accounts/{account-number}/transactions
- description: Verify if receiving bank supports RTP
  method: GET
  name: check-rtp-eligibility
  path: /v1/rtp/eligibility
- description: Send an instant RTP payment
  method: POST
  name: send-rtp-payment
  path: /v1/rtp/payments
- description: Get RTP payment status
  method: GET
  name: get-rtp-payment-status
  path: /v1/rtp/payments/{transaction-id}
personas: []
provider_name: US Bancorp
provider_slug: us-bancorp
search_terms:
- verify rtp eligibility
- get intraday transactions for an account to monitor payment activity
- get account transaction history by date range
- check rtp network eligibility
- check the status of a previously submitted rtp payment
- corporate banking
- get previous balances
- get current day transactions
- verify if receiving bank supports rtp
- list bank accounts
- get current day balances
- get current day balances for accounts
- account transaction history
- open banking
- send an instant rtp credit transfer payment to a recipient (irrevocable)
- get current balances
- banking
- account information
- send instant payment
- payments
- finance
- previous day account balances
- list accounts
- check rtp eligibility
- corporate deposit accounts
- check if a recipient bank participates in the rtp network before sending a payment
- real-time payments
- get previous day balances
- get account transactions history
- send rtp payment
- send an instant rtp payment
- current day account balances
- get previous business day account balances for reporting and reconciliation
- get historical transactions for an account for reconciliation and reporting
- get current day account balances for up to 50 accounts for cash positioning
- check payment status
- list u.s. bank corporate deposit accounts for cash position visibility
- get previous day balances for accounts
- consumer banking
- rtp real-time payments
- treasury management
- fortune 500
- get transactions
- get rtp payment status
- rtp payment status
- list all corporate deposit accounts
slug: treasury-management
source_filename: treasury-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"US Bank Treasury Management\"\n  description: >-\n    Unified treasury management capability composing US Bank Corporate Account Information\n    and RTP Real-Time Payments APIs. Used by corporate treasury teams, ERP systems, and\n    financial operations for account visibility, payment reconciliation, and real-time\n    payment origination.\n  tags:\n    - Banking\n    - Treasury Management\n    - Corporate Banking\n    - Payments\n    - Account Information\n    - Real-Time Payments\n    - Finance\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      USB_OAUTH_TOKEN: USB_OAUTH_TOKEN\n      USB_CLIENT_ID: USB_CLIENT_ID\n      USB_CLIENT_SECRET: USB_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: usb-accounts\n      location: ./shared/corporate-account-information.yaml\n    - import: usb-rtp\n      location: ./shared/rtp-payments.yaml\n\n  exposes:\n    - type: rest\n   \
  \   port: 8080\n      namespace: treasury-management-api\n      description: \"Unified REST API for US Bank treasury management operations.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: \"Corporate deposit accounts\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List all corporate deposit accounts\"\n              call: \"usb-accounts.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/balances/current\n          name: current-day-balances\n          description: \"Current day account balances\"\n          operations:\n            - method: GET\n              name: get-current-balances\n              description: \"Get current day balances for accounts\"\n              call: \"usb-accounts.get-current-day-balances\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/balances/previous\n          name: previous-day-balances\n          description: \"Previous day account balances\"\n          operations:\n            - method: GET\n              name: get-previous-balances\n              description: \"Get previous day balances for accounts\"\n              call: \"usb-accounts.get-previous-day-balances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{account-number}/transactions\n          name: transactions\n          description: \"Account transaction history\"\n          operations:\n            - method: GET\n              name: get-transactions\n              description: \"Get account transaction history by date range\"\n              call: \"usb-accounts.get-account-transactions\"\n              with:\n                accountNumber: \"rest.account-number\"\n                fromDate: \"rest.fromDate\"\n\
  \                toDate: \"rest.toDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/rtp/eligibility\n          name: rtp-eligibility\n          description: \"Check RTP network eligibility\"\n          operations:\n            - method: GET\n              name: check-rtp-eligibility\n              description: \"Verify if receiving bank supports RTP\"\n              call: \"usb-rtp.check-rtp-eligibility\"\n              with:\n                routingNumber: \"rest.routingNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/rtp/payments\n          name: rtp-payments\n          description: \"RTP real-time payments\"\n          operations:\n            - method: POST\n              name: send-rtp-payment\n              description: \"Send an instant RTP payment\"\n              call: \"usb-rtp.initiate-rtp-credit-transfer\"\n     \
  \         outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/rtp/payments/{transaction-id}\n          name: rtp-payment-status\n          description: \"RTP payment status\"\n          operations:\n            - method: GET\n              name: get-rtp-payment-status\n              description: \"Get RTP payment status\"\n              call: \"usb-rtp.get-rtp-credit-transfer-status\"\n              with:\n                transactionId: \"rest.transaction-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: treasury-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted US Bank treasury management and payment operations.\"\n      tools:\n        - name: list-bank-accounts\n          description: \"List U.S. Bank corporate deposit accounts for cash position visibility\"\n          hints:\n     \
  \       readOnly: true\n            openWorld: false\n          call: \"usb-accounts.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-current-day-balances\n          description: \"Get current day account balances for up to 50 accounts for cash positioning\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usb-accounts.get-current-day-balances\"\n          with:\n            accountNumbers: \"tools.accountNumbers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-previous-day-balances\n          description: \"Get previous business day account balances for reporting and reconciliation\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usb-accounts.get-previous-day-balances\"\n          with:\n            accountNumbers: \"tools.accountNumbers\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-current-day-transactions\n          description: \"Get intraday transactions for an account to monitor payment activity\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usb-accounts.get-current-day-transactions\"\n          with:\n            accountNumber: \"tools.accountNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-account-transactions-history\n          description: \"Get historical transactions for an account for reconciliation and reporting\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usb-accounts.get-account-transactions\"\n          with:\n            accountNumber: \"tools.accountNumber\"\n            fromDate: \"tools.fromDate\"\n            toDate: \"tools.toDate\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n\n        - name: verify-rtp-eligibility\n          description: \"Check if a recipient bank participates in the RTP Network before sending a payment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usb-rtp.check-rtp-eligibility\"\n          with:\n            routingNumber: \"tools.routingNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: send-instant-payment\n          description: \"Send an instant RTP credit transfer payment to a recipient (irrevocable)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"usb-rtp.initiate-rtp-credit-transfer\"\n          with:\n            payerAccountNumber: \"tools.payerAccountNumber\"\n            payeeAccountNumber: \"tools.payeeAccountNumber\"\n            payeeRoutingNumber: \"tools.payeeRoutingNumber\"\n            payeeName:\
  \ \"tools.payeeName\"\n            amount: \"tools.amount\"\n            remittanceInfo: \"tools.remittanceInfo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-payment-status\n          description: \"Check the status of a previously submitted RTP payment\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usb-rtp.get-rtp-credit-transfer-status\"\n          with:\n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-bancorp/refs/heads/main/capabilities/treasury-management.yaml
tags:
- Banking
- Treasury Management
- Corporate Banking
- Payments
- Account Information
- Real-Time Payments
- Finance
tools:
- description: List U.S. Bank corporate deposit accounts for cash position visibility
  hints:
    openWorld: false
    readOnly: true
  name: list-bank-accounts
- description: Get current day account balances for up to 50 accounts for cash positioning
  hints:
    openWorld: false
    readOnly: true
  name: get-current-day-balances
- description: Get previous business day account balances for reporting and reconciliation
  hints:
    openWorld: false
    readOnly: true
  name: get-previous-day-balances
- description: Get intraday transactions for an account to monitor payment activity
  hints:
    openWorld: false
    readOnly: true
  name: get-current-day-transactions
- description: Get historical transactions for an account for reconciliation and reporting
  hints:
    openWorld: false
    readOnly: true
  name: get-account-transactions-history
- description: Check if a recipient bank participates in the RTP Network before sending a payment
  hints:
    openWorld: true
    readOnly: true
  name: verify-rtp-eligibility
- description: Send an instant RTP credit transfer payment to a recipient (irrevocable)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-instant-payment
- description: Check the status of a previously submitted RTP payment
  hints:
    openWorld: false
    readOnly: true
  name: check-payment-status
---
