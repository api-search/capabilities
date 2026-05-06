---
categories: []
consumed_apis: []
description: Workflow capability for international money transfer and batch payment processing via Western Union's global payment network. Covers FX rate quoting, batch creation, payment submission, and status tracking across 200+ countries in 130+ currencies. Designed for financial institutions, ERP integrations, and enterprise payment workflows.
layout: capability
name: Western Union International Payments
operations:
- description: Check holding balance for a specific currency.
  method: GET
  name: get-holding-balance
  path: /v1/balances/{currency}
- description: Generate a foreign exchange rate quote.
  method: POST
  name: create-quote
  path: /v1/quotes
- description: Create a new payment batch.
  method: PUT
  name: create-batch
  path: /v1/batches/{batchId}
- description: Get batch status and summary.
  method: GET
  name: get-batch
  path: /v1/batches/{batchId}
- description: Delete an uncommitted batch.
  method: DELETE
  name: delete-batch
  path: /v1/batches/{batchId}
- description: Add an international payment to a batch.
  method: POST
  name: create-payment
  path: /v1/batches/{batchId}/payments
- description: List all payments in a batch.
  method: GET
  name: list-payments
  path: /v1/batches/{batchId}/payments
personas: []
provider_name: western-union
provider_slug: western-union
search_terms:
- foreign exchange
- get batch status
- add and list payments within a batch.
- create quote
- get batch status and summary.
- create and manage payment batches.
- generate fx rate quotes before initiating payments.
- financial services
- add an international payment to an existing batch. specify recipient details, bank account, amount, and currency. supports 130+ currencies in 200+ countries.
- get holding balance
- delete payment batch
- create batch
- list batch payments
- get fx quote
- create a new payment batch for grouping international payments. payments can be added to the batch before committing for processing.
- list all payments within a batch and their current statuses (received, accepted, rejected, processed).
- list payments
- get batch
- delete batch
- check balance
- add payment to batch
- check the holding balance for a specific currency in the western union account before initiating payments.
- list all payments in a batch.
- money transfer
- delete an uncommitted batch.
- create payment batch
- get a foreign exchange rate quote from western union for converting between currencies. returns rate, inverted rate, and settlement amount. valid for 5 minutes.
- international
- payments
- create a new payment batch.
- add an international payment to a batch.
- get the current status of a payment batch including counts of received vs. accepted payments and aggregate currency amounts.
- check holding balance for a specific currency.
- batch payments
- check available balance for a currency.
- create payment
- delete an uncommitted payment batch. cannot delete batches that have already been submitted for processing.
- generate a foreign exchange rate quote.
slug: international-payments
source_filename: international-payments.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Western Union International Payments\n  description: Workflow capability for international money transfer and batch payment processing via Western Union's global\n    payment network. Covers FX rate quoting, batch creation, payment submission, and status tracking across 200+ countries\n    in 130+ currencies. Designed for financial institutions, ERP integrations, and enterprise payment workflows.\n  tags:\n  - Money Transfer\n  - Payments\n  - International\n  - Batch Payments\n  - Foreign Exchange\n  - Financial Services\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WU_CLIENT_ID: WU_CLIENT_ID\n    WU_CERTIFICATE_PATH: WU_CERTIFICATE_PATH\n    WU_CERTIFICATE_PASSWORD: WU_CERTIFICATE_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: wu-mass-payments\n    baseUri: https://api.westernunion.com\n    description: Western Union Mass Payments API for international batch payments.\n\
  \    authentication:\n      type: certificate\n      certPath: '{{WU_CERTIFICATE_PATH}}'\n      certPassword: '{{WU_CERTIFICATE_PASSWORD}}'\n    resources:\n    - name: health\n      path: /Ping\n      description: API health check.\n      operations:\n      - name: ping\n        method: GET\n        description: Check API availability and mTLS credentials.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer\n      path: /customers/{clientId}\n      description: Customer account details.\n      operations:\n      - name: get-customer\n        method: GET\n        description: Get partner customer account details.\n        inputParameters:\n        - name: clientId\n          in: path\n          type: string\n          required: true\n          description: Western Union client ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n    - name: holding-balance\n      path: /HoldingBalance/{clientId}/{currencyCode}\n      description: Currency holding balance.\n      operations:\n      - name: get-holding-balance\n        method: GET\n        description: Get holding balance for a specific currency.\n        inputParameters:\n        - name: clientId\n          in: path\n          type: string\n          required: true\n          description: Western Union client ID.\n        - name: currencyCode\n          in: path\n          type: string\n          required: true\n          description: ISO 4217 currency code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch\n      path: /customers/{clientId}/batches/{batchId}\n      description: Payment batch management.\n      operations:\n      - name: get-batch\n        method: GET\n        description: Get batch details and status.\n        inputParameters:\n \
  \       - name: clientId\n          in: path\n          type: string\n          required: true\n          description: Western Union client ID.\n        - name: batchId\n          in: path\n          type: string\n          required: true\n          description: Batch identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-batch\n        method: PUT\n        description: Create a new payment batch.\n        inputParameters:\n        - name: clientId\n          in: path\n          type: string\n          required: true\n          description: Western Union client ID.\n        - name: batchId\n          in: path\n          type: string\n          required: true\n          description: Partner-assigned batch ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            reference: '{{tools.reference}}'\n      - name: delete-batch\n        method: DELETE\n        description: Delete an uncommitted batch.\n        inputParameters:\n        - name: clientId\n          in: path\n          type: string\n          required: true\n          description: Western Union client ID.\n        - name: batchId\n          in: path\n          type: string\n          required: true\n          description: Batch identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments\n      path: /customers/{clientId}/batches/{batchId}/payments\n      description: Payments within a batch.\n      operations:\n      - name: list-payments\n        method: GET\n        description: List all payments in a batch.\n        inputParameters:\n        - name: clientId\n          in: path\n          type: string\n          required: true\n          description: Western Union client\
  \ ID.\n        - name: batchId\n          in: path\n          type: string\n          required: true\n          description: Batch identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment\n        method: POST\n        description: Add a payment to an existing batch.\n        inputParameters:\n        - name: clientId\n          in: path\n          type: string\n          required: true\n          description: Western Union client ID.\n        - name: batchId\n          in: path\n          type: string\n          required: true\n          description: Batch identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            partnerReference: '{{tools.partnerReference}}'\n            amount: '{{tools.amount}}'\n            currencyCode: '{{tools.currencyCode}}'\n\
  \            beneficiary: '{{tools.beneficiary}}'\n            bankAccount: '{{tools.bankAccount}}'\n    - name: quotes\n      path: /customers/{clientId}/quotes\n      description: FX rate quotes.\n      operations:\n      - name: create-quote\n        method: POST\n        description: Generate an FX rate quote for currency conversion.\n        inputParameters:\n        - name: clientId\n          in: path\n          type: string\n          required: true\n          description: Western Union client ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            tradeCurrency: '{{tools.tradeCurrency}}'\n            settlementCurrency: '{{tools.settlementCurrency}}'\n            tradeAmount: '{{tools.tradeAmount}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wu-international-payments-api\n    description: Unified REST API for Western Union\
  \ international payment workflows.\n    resources:\n    - path: /v1/balances/{currency}\n      name: balance\n      description: Check available balance for a currency.\n      operations:\n      - method: GET\n        name: get-holding-balance\n        description: Check holding balance for a specific currency.\n        call: wu-mass-payments.get-holding-balance\n        with:\n          clientId: env.WU_CLIENT_ID\n          currencyCode: rest.currency\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quotes\n      name: quotes\n      description: Generate FX rate quotes before initiating payments.\n      operations:\n      - method: POST\n        name: create-quote\n        description: Generate a foreign exchange rate quote.\n        call: wu-mass-payments.create-quote\n        with:\n          clientId: env.WU_CLIENT_ID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batches/{batchId}\n      name: batch\n\
  \      description: Create and manage payment batches.\n      operations:\n      - method: PUT\n        name: create-batch\n        description: Create a new payment batch.\n        call: wu-mass-payments.create-batch\n        with:\n          clientId: env.WU_CLIENT_ID\n          batchId: rest.batchId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-batch\n        description: Get batch status and summary.\n        call: wu-mass-payments.get-batch\n        with:\n          clientId: env.WU_CLIENT_ID\n          batchId: rest.batchId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-batch\n        description: Delete an uncommitted batch.\n        call: wu-mass-payments.delete-batch\n        with:\n          clientId: env.WU_CLIENT_ID\n          batchId: rest.batchId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/batches/{batchId}/payments\n\
  \      name: payments\n      description: Add and list payments within a batch.\n      operations:\n      - method: POST\n        name: create-payment\n        description: Add an international payment to a batch.\n        call: wu-mass-payments.create-payment\n        with:\n          clientId: env.WU_CLIENT_ID\n          batchId: rest.batchId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-payments\n        description: List all payments in a batch.\n        call: wu-mass-payments.list-payments\n        with:\n          clientId: env.WU_CLIENT_ID\n          batchId: rest.batchId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wu-international-payments-mcp\n    transport: http\n    description: MCP server for AI-assisted international payment processing via Western Union.\n    tools:\n    - name: check-balance\n      description: Check the holding\
  \ balance for a specific currency in the Western Union account before initiating payments.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wu-mass-payments.get-holding-balance\n      with:\n        clientId: env.WU_CLIENT_ID\n        currencyCode: tools.currency\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fx-quote\n      description: Get a foreign exchange rate quote from Western Union for converting between currencies. Returns rate, inverted\n        rate, and settlement amount. Valid for 5 minutes.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wu-mass-payments.create-quote\n      with:\n        clientId: env.WU_CLIENT_ID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-payment-batch\n      description: Create a new payment batch for grouping international payments. Payments can be added to the batch before\n        committing for processing.\n   \
  \   hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: wu-mass-payments.create-batch\n      with:\n        clientId: env.WU_CLIENT_ID\n        batchId: tools.batchId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-payment-to-batch\n      description: Add an international payment to an existing batch. Specify recipient details, bank account, amount, and\n        currency. Supports 130+ currencies in 200+ countries.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wu-mass-payments.create-payment\n      with:\n        clientId: env.WU_CLIENT_ID\n        batchId: tools.batchId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-batch-payments\n      description: List all payments within a batch and their current statuses (received, accepted, rejected, processed).\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: wu-mass-payments.list-payments\n      with:\n        clientId: env.WU_CLIENT_ID\n        batchId: tools.batchId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-batch-status\n      description: Get the current status of a payment batch including counts of received vs. accepted payments and aggregate\n        currency amounts.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wu-mass-payments.get-batch\n      with:\n        clientId: env.WU_CLIENT_ID\n        batchId: tools.batchId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-payment-batch\n      description: Delete an uncommitted payment batch. Cannot delete batches that have already been submitted for processing.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: wu-mass-payments.delete-batch\n      with:\n        clientId: env.WU_CLIENT_ID\n        batchId:\
  \ tools.batchId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/western-union/refs/heads/main/capabilities/international-payments.yaml
tags:
- Money Transfer
- Payments
- International
- Batch Payments
- Foreign Exchange
- Financial Services
tools:
- description: Check the holding balance for a specific currency in the Western Union account before initiating payments.
  hints:
    openWorld: true
    readOnly: true
  name: check-balance
- description: Get a foreign exchange rate quote from Western Union for converting between currencies. Returns rate, inverted rate, and settlement amount. Valid for 5 minutes.
  hints:
    openWorld: false
    readOnly: true
  name: get-fx-quote
- description: Create a new payment batch for grouping international payments. Payments can be added to the batch before committing for processing.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: create-payment-batch
- description: Add an international payment to an existing batch. Specify recipient details, bank account, amount, and currency. Supports 130+ currencies in 200+ countries.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-payment-to-batch
- description: List all payments within a batch and their current statuses (received, accepted, rejected, processed).
  hints:
    openWorld: true
    readOnly: true
  name: list-batch-payments
- description: Get the current status of a payment batch including counts of received vs. accepted payments and aggregate currency amounts.
  hints:
    openWorld: true
    readOnly: true
  name: get-batch-status
- description: Delete an uncommitted payment batch. Cannot delete batches that have already been submitted for processing.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-payment-batch
---
