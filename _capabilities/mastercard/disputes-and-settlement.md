---
categories: []
consumed_apis: []
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
- look up transaction details for dispute resolution
- fraud detection
- look up transaction details to aid dispute resolution
- lookup transaction for dispute
- retrieve chargebacks from mastercom
- create retrieval request
- financial services
- get chargebacks
- create a chargeback in mastercom
- settlement
- authorize transaction
- create a retrieval request in mastercom
- transaction clarity for dispute resolution
- create a retrieval request
- credit cards
- authorize a transaction through core processing
- retrieve chargebacks
- digital identity
- open banking
- mastercom
- chargeback management
- disputes
- create a chargeback
- mastercard
- payments
- get currency conversion rate for settlement
- chargebacks
- lookup transaction clarity
- create retrieval
- get settlement rate
- retrieval request management
- create chargeback
slug: disputes-and-settlement
source_filename: disputes-and-settlement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Disputes and Settlement\n  description: Unified workflow for dispute managers and back-office teams to manage chargebacks, retrieval requests, transaction\n    processing, and settlement through Mastercom and processing APIs.\n  tags:\n  - Mastercard\n  - Disputes\n  - Chargebacks\n  - Settlement\n  - Mastercom\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: mastercom\n    baseUri: https://api.mastercard.com/mastercom\n    description: Mastercard Mastercom API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: chargebacks\n      path: /chargebacks\n      description: Chargeback management\n      operations:\n  \
  \    - name: create-chargeback\n        method: POST\n        description: Create a chargeback\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            chargeback: '{{tools.chargeback}}'\n      - name: get-chargebacks\n        method: GET\n        description: Retrieve chargebacks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: retrievals\n      path: /retrievals\n      description: Retrieval request management\n      operations:\n      - name: create-retrieval\n        method: POST\n        description: Create a retrieval request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            retrieval: '{{tools.retrieval}}'\n  - type:\
  \ http\n    namespace: processing-core\n    baseUri: https://api.mastercard.com/processing/core\n    description: Mastercard Processing Core API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: authorizations\n      path: /authorizations\n      description: Transaction authorization\n      operations:\n      - name: authorize\n        method: POST\n        description: Authorize a transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            authorization: '{{tools.authorization}}'\n  - type: http\n    namespace: ethoca-consumer-clarity\n    baseUri: https://api.mastercard.com/ethoca/consumer-clarity\n    description: Mastercard Ethoca Consumer Clarity API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n\
  \      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: transactions\n      path: /transactions\n      description: Transaction clarity lookups\n      operations:\n      - name: lookup-transaction\n        method: POST\n        description: Look up transaction details for dispute resolution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transaction: '{{tools.transaction}}'\n  - type: http\n    namespace: currency-conversion\n    baseUri: https://api.mastercard.com/settlement/currencyrate\n    description: Mastercard Currency Conversion API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: rates\n      path: /rates\n      description: Currency conversion rates\n      operations:\n      - name: get-conversion-rate\n\
  \        method: GET\n        description: Get currency conversion rate\n        inputParameters:\n        - name: fxDate\n          in: query\n          type: string\n          required: true\n          description: Date for the conversion rate\n        - name: transCurr\n          in: query\n          type: string\n          required: true\n          description: Transaction currency\n        - name: crdhldBillCurr\n          in: query\n          type: string\n          required: true\n          description: Cardholder billing currency\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8092\n    namespace: disputes-settlement-api\n    description: Unified REST API for dispute management and settlement.\n    resources:\n    - path: /v1/chargebacks\n      name: chargebacks\n      description: Chargeback management\n      operations:\n      - method: POST\n        name: create-chargeback\n\
  \        description: Create a chargeback\n        call: mastercom.create-chargeback\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-chargebacks\n        description: Retrieve chargebacks\n        call: mastercom.get-chargebacks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/retrievals\n      name: retrievals\n      description: Retrieval request management\n      operations:\n      - method: POST\n        name: create-retrieval\n        description: Create a retrieval request\n        call: mastercom.create-retrieval\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transaction-clarity\n      name: transaction-clarity\n      description: Transaction clarity for dispute resolution\n      operations:\n      - method: POST\n        name: lookup-transaction-clarity\n        description: Look up transaction details for dispute resolution\n \
  \       call: ethoca-consumer-clarity.lookup-transaction\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9102\n    namespace: disputes-settlement-mcp\n    transport: http\n    description: MCP server for AI-assisted dispute management and settlement.\n    tools:\n    - name: create-chargeback\n      description: Create a chargeback in Mastercom\n      hints:\n        readOnly: false\n      call: mastercom.create-chargeback\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-chargebacks\n      description: Retrieve chargebacks from Mastercom\n      hints:\n        readOnly: true\n      call: mastercom.get-chargebacks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-retrieval-request\n      description: Create a retrieval request in Mastercom\n      hints:\n        readOnly: false\n      call: mastercom.create-retrieval\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: lookup-transaction-for-dispute\n      description: Look up transaction details to aid dispute resolution\n      hints:\n        readOnly: true\n      call: ethoca-consumer-clarity.lookup-transaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authorize-transaction\n      description: Authorize a transaction through core processing\n      hints:\n        readOnly: false\n      call: processing-core.authorize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-settlement-rate\n      description: Get currency conversion rate for settlement\n      hints:\n        readOnly: true\n        idempotent: true\n      call: currency-conversion.get-conversion-rate\n      with:\n        fxDate: tools.fxDate\n        transCurr: tools.transCurr\n        crdhldBillCurr: tools.crdhldBillCurr\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
