---
categories: []
consumed_apis:
- mastercom
- processing-core
- ethoca-consumer-clarity
- currency-conversion
description: Unified workflow for dispute managers and back-office teams to manage chargebacks, retrieval requests, transaction processing, and settlement through Mastercom and processing APIs.
layout: capability
name: Mastercard Disputes and Settlement
operations:
- description: Create a chargeback
  method: POST
  name: create-chargeback
  path: /v1/chargebacks
- description: Retrieve chargebacks
  method: GET
  name: get-chargebacks
  path: /v1/chargebacks
- description: Create a retrieval request
  method: POST
  name: create-retrieval
  path: /v1/retrievals
- description: Look up transaction details for dispute resolution
  method: POST
  name: lookup-transaction-clarity
  path: /v1/transaction-clarity
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- retrieve chargebacks from mastercom
- payments
- open banking
- retrieve chargebacks
- get currency conversion rate for settlement
- get settlement rate
- settlement
- lookup transaction for dispute
- digital identity
- chargeback management
- lookup transaction clarity
- create retrieval
- mastercard
- create a retrieval request in mastercom
- create a chargeback in mastercom
- create retrieval request
- retrieval request management
- transaction clarity for dispute resolution
- financial services
- create a retrieval request
- mastercom
- create chargeback
- chargebacks
- fraud detection
- create a chargeback
- look up transaction details to aid dispute resolution
- authorize a transaction through core processing
- authorize transaction
- disputes
- get chargebacks
- credit cards
- look up transaction details for dispute resolution
slug: disputes-and-settlement
source_filename: disputes-and-settlement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Mastercard Disputes and Settlement\"\n  description: \"Unified workflow for dispute managers and back-office teams to manage chargebacks, retrieval requests, transaction processing, and settlement through Mastercom and processing APIs.\"\n  tags:\n    - Mastercard\n    - Disputes\n    - Chargebacks\n    - Settlement\n    - Mastercom\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n      MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\n\ncapability:\n  consumes:\n    - import: mastercom\n      location: ./shared/mastercom.yaml\n    - import: processing-core\n      location: ./shared/processing-core.yaml\n    - import: ethoca-consumer-clarity\n      location: ./shared/ethoca-consumer-clarity.yaml\n    - import: currency-conversion\n      location: ./shared/currency-conversion.yaml\n\n  exposes:\n    - type: rest\n      port: 8092\n\
  \      namespace: disputes-settlement-api\n      description: \"Unified REST API for dispute management and settlement.\"\n      resources:\n        - path: /v1/chargebacks\n          name: chargebacks\n          description: \"Chargeback management\"\n          operations:\n            - method: POST\n              name: create-chargeback\n              description: \"Create a chargeback\"\n              call: \"mastercom.create-chargeback\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-chargebacks\n              description: \"Retrieve chargebacks\"\n              call: \"mastercom.get-chargebacks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/retrievals\n          name: retrievals\n          description: \"Retrieval request management\"\n          operations:\n            - method: POST\n              name:\
  \ create-retrieval\n              description: \"Create a retrieval request\"\n              call: \"mastercom.create-retrieval\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transaction-clarity\n          name: transaction-clarity\n          description: \"Transaction clarity for dispute resolution\"\n          operations:\n            - method: POST\n              name: lookup-transaction-clarity\n              description: \"Look up transaction details for dispute resolution\"\n              call: \"ethoca-consumer-clarity.lookup-transaction\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9102\n      namespace: disputes-settlement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted dispute management and settlement.\"\n      tools:\n        - name: create-chargeback\n          description: \"Create a\
  \ chargeback in Mastercom\"\n          hints:\n            readOnly: false\n          call: \"mastercom.create-chargeback\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-chargebacks\n          description: \"Retrieve chargebacks from Mastercom\"\n          hints:\n            readOnly: true\n          call: \"mastercom.get-chargebacks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-retrieval-request\n          description: \"Create a retrieval request in Mastercom\"\n          hints:\n            readOnly: false\n          call: \"mastercom.create-retrieval\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-transaction-for-dispute\n          description: \"Look up transaction details to aid dispute resolution\"\n          hints:\n            readOnly: true\n          call: \"ethoca-consumer-clarity.lookup-transaction\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: authorize-transaction\n          description: \"Authorize a transaction through core processing\"\n          hints:\n            readOnly: false\n          call: \"processing-core.authorize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-settlement-rate\n          description: \"Get currency conversion rate for settlement\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"currency-conversion.get-conversion-rate\"\n          with:\n            fxDate: \"tools.fxDate\"\n            transCurr: \"tools.transCurr\"\n            crdhldBillCurr: \"tools.crdhldBillCurr\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/disputes-and-settlement.yaml
tags:
- Mastercard
- Disputes
- Chargebacks
- Settlement
- Mastercom
tools:
- description: Create a chargeback in Mastercom
  hints:
    readOnly: false
  name: create-chargeback
- description: Retrieve chargebacks from Mastercom
  hints:
    readOnly: true
  name: get-chargebacks
- description: Create a retrieval request in Mastercom
  hints:
    readOnly: false
  name: create-retrieval-request
- description: Look up transaction details to aid dispute resolution
  hints:
    readOnly: true
  name: lookup-transaction-for-dispute
- description: Authorize a transaction through core processing
  hints:
    readOnly: false
  name: authorize-transaction
- description: Get currency conversion rate for settlement
  hints:
    idempotent: true
    readOnly: true
  name: get-settlement-rate
---
