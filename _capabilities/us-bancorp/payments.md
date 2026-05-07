---
categories: []
consumed_apis: []
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
- rtp payment status
- verify if a bank participates in the rtp network before initiating payment
- rtp network eligibility check
- verify rtp eligibility by routing number
- track rtp payment
- disbursements
- send an instant, irrevocable rtp credit transfer via the clearing house
- track the status of a sent rtp credit transfer
- check rtp eligibility
- send an instant rtp credit transfer (irrevocable)
- finance
- verify rtp eligibility
- get rtp status
- instant rtp credit transfer payments
- fraud prevention
- get rtp payment status
- consumer banking
- rtp
- corporate banking
- treasury management
- push to card
- open banking
- banking
- send rtp credit transfer
- payments
- fortune 500
- send rtp payment
slug: payments
source_filename: payments.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: US Bank Payments\n  description: Unified payments capability composing US Bank RTP, Push to Card, and Positive Pay APIs. Used by payments teams\n    and corporate finance for real-time payment origination, instant card disbursements, and check fraud prevention.\n  tags:\n  - Banking\n  - Payments\n  - RTP\n  - Push to Card\n  - Fraud Prevention\n  - Finance\n  - Disbursements\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    USB_OAUTH_TOKEN: USB_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: usb-rtp\n    baseUri: https://api.usbank.com/v1\n    description: US Bank RTP Real-Time Payments API\n    authentication:\n      type: bearer\n      token: '{{USB_OAUTH_TOKEN}}'\n    resources:\n    - name: rtp-eligibility\n      path: /rtp/eligibility\n      description: Check if a bank supports RTP\n      operations:\n      - name: check-rtp-eligibility\n        method: GET\n       \
  \ description: Check if a receiving bank is part of the RTP Network\n        inputParameters:\n        - name: routingNumber\n          in: query\n          type: string\n          required: true\n          description: 9-digit routing number of receiving bank\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rtp-credit-transfers\n      path: /rtp/credit-transfers\n      description: RTP credit transfer payments\n      operations:\n      - name: initiate-rtp-credit-transfer\n        method: POST\n        description: Initiate an RTP credit transfer (instant, irrevocable)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payerAccountNumber: '{{tools.payerAccountNumber}}'\n            payeeAccountNumber: '{{tools.payeeAccountNumber}}'\n            payeeRoutingNumber:\
  \ '{{tools.payeeRoutingNumber}}'\n            payeeName: '{{tools.payeeName}}'\n            amount: '{{tools.amount}}'\n            remittanceInfo: '{{tools.remittanceInfo}}'\n      - name: get-rtp-credit-transfer-status\n        method: GET\n        description: Get status of an RTP credit transfer\n        inputParameters:\n        - name: transactionId\n          in: path\n          type: string\n          required: true\n          description: Transaction identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rtp-requests-for-payment\n      path: /rtp/requests-for-payment\n      description: RTP Request for Payment (RFP)\n      operations:\n      - name: initiate-rtp-rfp\n        method: POST\n        description: Initiate an RTP Request for Payment to receive funds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            creditorAccountNumber: '{{tools.creditorAccountNumber}}'\n            debtorName: '{{tools.debtorName}}'\n            amount: '{{tools.amount}}'\n            dueDate: '{{tools.dueDate}}'\n      - name: get-rtp-rfp-status\n        method: GET\n        description: Get status of an RTP Request for Payment\n        inputParameters:\n        - name: requestId\n          in: path\n          type: string\n          required: true\n          description: RFP request identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: payments-api\n    description: Unified REST API for US Bank payment operations.\n    resources:\n    - path: /v1/rtp/eligibility\n      name: rtp-eligibility\n      description: RTP network eligibility check\n      operations:\n      - method: GET\n        name: check-rtp-eligibility\n\
  \        description: Verify RTP eligibility by routing number\n        call: usb-rtp.check-rtp-eligibility\n        with:\n          routingNumber: rest.routingNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rtp/credit-transfers\n      name: rtp-credit-transfers\n      description: Instant RTP credit transfer payments\n      operations:\n      - method: POST\n        name: send-rtp-payment\n        description: Send an instant RTP credit transfer (irrevocable)\n        call: usb-rtp.initiate-rtp-credit-transfer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rtp/credit-transfers/{transaction-id}\n      name: rtp-credit-transfer-status\n      description: RTP payment status\n      operations:\n      - method: GET\n        name: get-rtp-status\n        description: Get RTP payment status\n        call: usb-rtp.get-rtp-credit-transfer-status\n        with:\n          transactionId: rest.transaction-id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: payments-mcp\n    transport: http\n    description: MCP server for AI-assisted US Bank payment orchestration.\n    tools:\n    - name: verify-rtp-eligibility\n      description: Verify if a bank participates in the RTP Network before initiating payment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usb-rtp.check-rtp-eligibility\n      with:\n        routingNumber: tools.routingNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-rtp-credit-transfer\n      description: Send an instant, irrevocable RTP credit transfer via The Clearing House\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: usb-rtp.initiate-rtp-credit-transfer\n      with:\n        payerAccountNumber: tools.payerAccountNumber\n        payeeAccountNumber: tools.payeeAccountNumber\n\
  \        payeeRoutingNumber: tools.payeeRoutingNumber\n        payeeName: tools.payeeName\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-rtp-payment\n      description: Track the status of a sent RTP credit transfer\n      hints:\n        readOnly: true\n        openWorld: false\n      call: usb-rtp.get-rtp-credit-transfer-status\n      with:\n        transactionId: tools.transactionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
