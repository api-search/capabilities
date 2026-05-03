---
categories: []
consumed_apis:
- wu-mass-payments
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
- check balance
- get batch
- get batch status and summary.
- create a new payment batch.
- list payments
- foreign exchange
- delete payment batch
- delete batch
- get fx quote
- delete an uncommitted payment batch. cannot delete batches that have already been submitted for processing.
- create a new payment batch for grouping international payments. payments can be added to the batch before committing for processing.
- financial services
- create payment
- add payment to batch
- list all payments in a batch.
- get batch status
- payments
- add an international payment to an existing batch. specify recipient details, bank account, amount, and currency. supports 130+ currencies in 200+ countries.
- delete an uncommitted batch.
- create batch
- money transfer
- get the current status of a payment batch including counts of received vs. accepted payments and aggregate currency amounts.
- create payment batch
- check available balance for a currency.
- add an international payment to a batch.
- get holding balance
- check holding balance for a specific currency.
- generate fx rate quotes before initiating payments.
- generate a foreign exchange rate quote.
- check the holding balance for a specific currency in the western union account before initiating payments.
- international
- create and manage payment batches.
- batch payments
- add and list payments within a batch.
- list all payments within a batch and their current statuses (received, accepted, rejected, processed).
- list batch payments
- create quote
- get a foreign exchange rate quote from western union for converting between currencies. returns rate, inverted rate, and settlement amount. valid for 5 minutes.
slug: international-payments
source_filename: international-payments.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Western Union International Payments\"\n  description: >-\n    Workflow capability for international money transfer and batch payment\n    processing via Western Union's global payment network. Covers FX rate\n    quoting, batch creation, payment submission, and status tracking across\n    200+ countries in 130+ currencies. Designed for financial institutions,\n    ERP integrations, and enterprise payment workflows.\n  tags:\n    - Money Transfer\n    - Payments\n    - International\n    - Batch Payments\n    - Foreign Exchange\n    - Financial Services\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WU_CLIENT_ID: WU_CLIENT_ID\n      WU_CERTIFICATE_PATH: WU_CERTIFICATE_PATH\n      WU_CERTIFICATE_PASSWORD: WU_CERTIFICATE_PASSWORD\n\ncapability:\n  consumes:\n    - import: wu-mass-payments\n      location: ./shared/mass-payments.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8080\n      namespace: wu-international-payments-api\n      description: \"Unified REST API for Western Union international payment workflows.\"\n      resources:\n        - path: /v1/balances/{currency}\n          name: balance\n          description: Check available balance for a currency.\n          operations:\n            - method: GET\n              name: get-holding-balance\n              description: Check holding balance for a specific currency.\n              call: \"wu-mass-payments.get-holding-balance\"\n              with:\n                clientId: \"env.WU_CLIENT_ID\"\n                currencyCode: \"rest.currency\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/quotes\n          name: quotes\n          description: Generate FX rate quotes before initiating payments.\n          operations:\n            - method: POST\n              name: create-quote\n              description: Generate a foreign\
  \ exchange rate quote.\n              call: \"wu-mass-payments.create-quote\"\n              with:\n                clientId: \"env.WU_CLIENT_ID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/batches/{batchId}\n          name: batch\n          description: Create and manage payment batches.\n          operations:\n            - method: PUT\n              name: create-batch\n              description: Create a new payment batch.\n              call: \"wu-mass-payments.create-batch\"\n              with:\n                clientId: \"env.WU_CLIENT_ID\"\n                batchId: \"rest.batchId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-batch\n              description: Get batch status and summary.\n              call: \"wu-mass-payments.get-batch\"\n              with:\n                clientId: \"env.WU_CLIENT_ID\"\
  \n                batchId: \"rest.batchId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-batch\n              description: Delete an uncommitted batch.\n              call: \"wu-mass-payments.delete-batch\"\n              with:\n                clientId: \"env.WU_CLIENT_ID\"\n                batchId: \"rest.batchId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/batches/{batchId}/payments\n          name: payments\n          description: Add and list payments within a batch.\n          operations:\n            - method: POST\n              name: create-payment\n              description: Add an international payment to a batch.\n              call: \"wu-mass-payments.create-payment\"\n              with:\n                clientId: \"env.WU_CLIENT_ID\"\n                batchId: \"rest.batchId\"\n   \
  \           outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-payments\n              description: List all payments in a batch.\n              call: \"wu-mass-payments.list-payments\"\n              with:\n                clientId: \"env.WU_CLIENT_ID\"\n                batchId: \"rest.batchId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wu-international-payments-mcp\n      transport: http\n      description: \"MCP server for AI-assisted international payment processing via Western Union.\"\n      tools:\n        - name: check-balance\n          description: >-\n            Check the holding balance for a specific currency in the Western\n            Union account before initiating payments.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wu-mass-payments.get-holding-balance\"\
  \n          with:\n            clientId: \"env.WU_CLIENT_ID\"\n            currencyCode: \"tools.currency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-fx-quote\n          description: >-\n            Get a foreign exchange rate quote from Western Union for converting\n            between currencies. Returns rate, inverted rate, and settlement\n            amount. Valid for 5 minutes.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wu-mass-payments.create-quote\"\n          with:\n            clientId: \"env.WU_CLIENT_ID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-payment-batch\n          description: >-\n            Create a new payment batch for grouping international payments.\n            Payments can be added to the batch before committing for processing.\n          hints:\n            readOnly: false\n\
  \            destructive: false\n            idempotent: true\n          call: \"wu-mass-payments.create-batch\"\n          with:\n            clientId: \"env.WU_CLIENT_ID\"\n            batchId: \"tools.batchId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: add-payment-to-batch\n          description: >-\n            Add an international payment to an existing batch. Specify\n            recipient details, bank account, amount, and currency. Supports\n            130+ currencies in 200+ countries.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wu-mass-payments.create-payment\"\n          with:\n            clientId: \"env.WU_CLIENT_ID\"\n            batchId: \"tools.batchId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-batch-payments\n          description: >-\n            List\
  \ all payments within a batch and their current statuses\n            (received, accepted, rejected, processed).\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wu-mass-payments.list-payments\"\n          with:\n            clientId: \"env.WU_CLIENT_ID\"\n            batchId: \"tools.batchId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-batch-status\n          description: >-\n            Get the current status of a payment batch including counts of\n            received vs. accepted payments and aggregate currency amounts.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wu-mass-payments.get-batch\"\n          with:\n            clientId: \"env.WU_CLIENT_ID\"\n            batchId: \"tools.batchId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-payment-batch\n   \
  \       description: >-\n            Delete an uncommitted payment batch. Cannot delete batches that\n            have already been submitted for processing.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"wu-mass-payments.delete-batch\"\n          with:\n            clientId: \"env.WU_CLIENT_ID\"\n            batchId: \"tools.batchId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
