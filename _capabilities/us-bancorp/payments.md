---
categories: []
consumed_apis:
- usb-rtp
description: Unified payments capability composing US Bank RTP, Push to Card, and Positive Pay APIs. Used by payments teams and corporate finance for real-time payment origination, instant card disbursements, and check fraud prevention.
layout: capability
name: US Bank Payments
operations:
- description: Verify RTP eligibility by routing number
  method: GET
  name: check-rtp-eligibility
  path: /v1/rtp/eligibility
- description: Send an instant RTP credit transfer (irrevocable)
  method: POST
  name: send-rtp-payment
  path: /v1/rtp/credit-transfers
- description: Get RTP payment status
  method: GET
  name: get-rtp-status
  path: /v1/rtp/credit-transfers/{transaction-id}
personas: []
provider_name: US Bancorp
provider_slug: us-bancorp
search_terms:
- verify rtp eligibility
- disbursements
- corporate banking
- send an instant rtp credit transfer (irrevocable)
- track rtp payment
- get rtp status
- push to card
- verify rtp eligibility by routing number
- open banking
- send rtp credit transfer
- banking
- send an instant, irrevocable rtp credit transfer via the clearing house
- payments
- finance
- verify if a bank participates in the rtp network before initiating payment
- rtp
- check rtp eligibility
- rtp network eligibility check
- track the status of a sent rtp credit transfer
- instant rtp credit transfer payments
- send rtp payment
- consumer banking
- fraud prevention
- fortune 500
- treasury management
- get rtp payment status
- rtp payment status
slug: payments
source_filename: payments.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"US Bank Payments\"\n  description: >-\n    Unified payments capability composing US Bank RTP, Push to Card, and Positive Pay APIs.\n    Used by payments teams and corporate finance for real-time payment origination, instant\n    card disbursements, and check fraud prevention.\n  tags:\n    - Banking\n    - Payments\n    - RTP\n    - Push to Card\n    - Fraud Prevention\n    - Finance\n    - Disbursements\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      USB_OAUTH_TOKEN: USB_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: usb-rtp\n      location: ./shared/rtp-payments.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: payments-api\n      description: \"Unified REST API for US Bank payment operations.\"\n      resources:\n        - path: /v1/rtp/eligibility\n          name: rtp-eligibility\n          description: \"RTP network eligibility check\"\n\
  \          operations:\n            - method: GET\n              name: check-rtp-eligibility\n              description: \"Verify RTP eligibility by routing number\"\n              call: \"usb-rtp.check-rtp-eligibility\"\n              with:\n                routingNumber: \"rest.routingNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/rtp/credit-transfers\n          name: rtp-credit-transfers\n          description: \"Instant RTP credit transfer payments\"\n          operations:\n            - method: POST\n              name: send-rtp-payment\n              description: \"Send an instant RTP credit transfer (irrevocable)\"\n              call: \"usb-rtp.initiate-rtp-credit-transfer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/rtp/credit-transfers/{transaction-id}\n          name: rtp-credit-transfer-status\n          description:\
  \ \"RTP payment status\"\n          operations:\n            - method: GET\n              name: get-rtp-status\n              description: \"Get RTP payment status\"\n              call: \"usb-rtp.get-rtp-credit-transfer-status\"\n              with:\n                transactionId: \"rest.transaction-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: payments-mcp\n      transport: http\n      description: \"MCP server for AI-assisted US Bank payment orchestration.\"\n      tools:\n        - name: verify-rtp-eligibility\n          description: \"Verify if a bank participates in the RTP Network before initiating payment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usb-rtp.check-rtp-eligibility\"\n          with:\n            routingNumber: \"tools.routingNumber\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n\n        - name: send-rtp-credit-transfer\n          description: \"Send an instant, irrevocable RTP credit transfer via The Clearing House\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"usb-rtp.initiate-rtp-credit-transfer\"\n          with:\n            payerAccountNumber: \"tools.payerAccountNumber\"\n            payeeAccountNumber: \"tools.payeeAccountNumber\"\n            payeeRoutingNumber: \"tools.payeeRoutingNumber\"\n            payeeName: \"tools.payeeName\"\n            amount: \"tools.amount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: track-rtp-payment\n          description: \"Track the status of a sent RTP credit transfer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usb-rtp.get-rtp-credit-transfer-status\"\n          with:\n            transactionId:\
  \ \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-bancorp/refs/heads/main/capabilities/payments.yaml
tags:
- Banking
- Payments
- RTP
- Push to Card
- Fraud Prevention
- Finance
- Disbursements
tools:
- description: Verify if a bank participates in the RTP Network before initiating payment
  hints:
    openWorld: true
    readOnly: true
  name: verify-rtp-eligibility
- description: Send an instant, irrevocable RTP credit transfer via The Clearing House
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-rtp-credit-transfer
- description: Track the status of a sent RTP credit transfer
  hints:
    openWorld: false
    readOnly: true
  name: track-rtp-payment
---
