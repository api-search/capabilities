---
categories: []
consumed_apis:
- tazama-tms
description: Workflow capability for real-time financial transaction fraud detection and AML compliance monitoring using the Tazama platform. Enables financial service providers to submit ISO 20022 transaction messages for immediate evaluation against configurable fraud detection rules and typology scoring.
layout: capability
name: Tazama Fraud Detection
operations:
- description: Check Tazama platform health status
  method: GET
  name: get-health
  path: /v1/health
- description: Submit credit transfer initiation (pain.001) for fraud and AML evaluation
  method: POST
  name: evaluate-credit-transfer
  path: /v1/transactions/credit-transfers
- description: Submit creditor payment activation request (pain.013) for evaluation
  method: POST
  name: evaluate-payment-activation
  path: /v1/transactions/payment-activations
- description: Submit FI-to-FI customer credit transfer (pacs.008) for fraud evaluation
  method: POST
  name: evaluate-interbank-transfer
  path: /v1/transactions/interbank-transfers
- description: Submit payment status report (pacs.002) for evaluation
  method: POST
  name: evaluate-payment-status
  path: /v1/transactions/payment-status
personas: []
provider_name: Tazama
provider_slug: tazama
search_terms:
- submit an iso 20022 pain.001.001.11 customer credit transfer initiation message for real-time fraud detection and aml screening. returns evaluation results from configured rule processors and typology scoring.
- tazama
- submit an iso 20022 pain.013.001.09 creditor payment activation request for fraud and aml evaluation. returns rule results and typology scores.
- submit payment status report (pacs.002) for evaluation
- real time
- service health monitoring
- submit an iso 20022 pacs.008.001.10 fi-to-fi customer credit transfer for real-time fraud detection. evaluates the transfer against all active typologies and returns risk assessment results.
- fi-to-fi interbank transfer evaluation
- customer credit transfer transaction evaluation
- evaluate payment status
- transaction monitoring
- open source
- evaluate interbank transfer
- payment status report evaluation
- linux foundation
- check tazama platform health status
- submit fi-to-fi customer credit transfer (pacs.008) for fraud evaluation
- anti-money laundering
- creditor payment activation request evaluation
- evaluate payment activation
- evaluate credit transfer
- submit credit transfer initiation (pain.001) for fraud and aml evaluation
- financial technology
- submit creditor payment activation request (pain.013) for evaluation
- check the operational status of the tazama fraud detection platform
- compliance
- check tazama health
- iso 20022
- fraud detection
- get health
- submit an iso 20022 pacs.002.001.12 payment status report for aml compliance evaluation and fraud pattern analysis.
slug: fraud-detection
source_filename: fraud-detection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tazama Fraud Detection\"\n  description: >-\n    Workflow capability for real-time financial transaction fraud detection and\n    AML compliance monitoring using the Tazama platform. Enables financial service\n    providers to submit ISO 20022 transaction messages for immediate evaluation\n    against configurable fraud detection rules and typology scoring.\n  tags:\n    - Tazama\n    - Financial Technology\n    - Fraud Detection\n    - Anti-Money Laundering\n    - ISO 20022\n    - Transaction Monitoring\n    - Compliance\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TAZAMA_API_KEY: TAZAMA_API_KEY\n\ncapability:\n  consumes:\n    - import: tazama-tms\n      location: ./shared/transaction-monitoring.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tazama-fraud-detection-api\n      description: \"Unified REST API for Tazama real-time fraud detection\
  \ and AML monitoring.\"\n      resources:\n        - path: /v1/health\n          name: health\n          description: \"Service health monitoring\"\n          operations:\n            - method: GET\n              name: get-health\n              description: \"Check Tazama platform health status\"\n              call: \"tazama-tms.get-health-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transactions/credit-transfers\n          name: credit-transfers\n          description: \"Customer credit transfer transaction evaluation\"\n          operations:\n            - method: POST\n              name: evaluate-credit-transfer\n              description: \"Submit credit transfer initiation (pain.001) for fraud and AML evaluation\"\n              call: \"tazama-tms.evaluate-pain001-transaction\"\n              with:\n                transaction: \"rest.body\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transactions/payment-activations\n          name: payment-activations\n          description: \"Creditor payment activation request evaluation\"\n          operations:\n            - method: POST\n              name: evaluate-payment-activation\n              description: \"Submit creditor payment activation request (pain.013) for evaluation\"\n              call: \"tazama-tms.evaluate-pain013-transaction\"\n              with:\n                transaction: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transactions/interbank-transfers\n          name: interbank-transfers\n          description: \"FI-to-FI interbank transfer evaluation\"\n          operations:\n            - method: POST\n              name: evaluate-interbank-transfer\n              description: \"Submit FI-to-FI customer credit transfer (pacs.008) for fraud\
  \ evaluation\"\n              call: \"tazama-tms.evaluate-pacs008-transaction\"\n              with:\n                transaction: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transactions/payment-status\n          name: payment-status\n          description: \"Payment status report evaluation\"\n          operations:\n            - method: POST\n              name: evaluate-payment-status\n              description: \"Submit payment status report (pacs.002) for evaluation\"\n              call: \"tazama-tms.evaluate-pacs002-transaction\"\n              with:\n                transaction: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tazama-fraud-detection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted fraud detection and AML compliance monitoring.\"\
  \n      tools:\n        - name: check-tazama-health\n          description: \"Check the operational status of the Tazama fraud detection platform\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tazama-tms.get-health-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: evaluate-credit-transfer\n          description: >-\n            Submit an ISO 20022 pain.001.001.11 customer credit transfer initiation\n            message for real-time fraud detection and AML screening. Returns evaluation\n            results from configured rule processors and typology scoring.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tazama-tms.evaluate-pain001-transaction\"\n          with:\n            transaction: \"tools.transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: evaluate-payment-activation\n          description: >-\n            Submit an ISO 20022 pain.013.001.09 creditor payment activation request\n            for fraud and AML evaluation. Returns rule results and typology scores.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tazama-tms.evaluate-pain013-transaction\"\n          with:\n            transaction: \"tools.transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: evaluate-interbank-transfer\n          description: >-\n            Submit an ISO 20022 pacs.008.001.10 FI-to-FI customer credit transfer\n            for real-time fraud detection. Evaluates the transfer against all active\n            typologies and returns risk assessment results.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call:\
  \ \"tazama-tms.evaluate-pacs008-transaction\"\n          with:\n            transaction: \"tools.transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: evaluate-payment-status\n          description: >-\n            Submit an ISO 20022 pacs.002.001.12 payment status report for AML\n            compliance evaluation and fraud pattern analysis.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tazama-tms.evaluate-pacs002-transaction\"\n          with:\n            transaction: \"tools.transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tazama/refs/heads/main/capabilities/fraud-detection.yaml
tags:
- Tazama
- Financial Technology
- Fraud Detection
- Anti-Money Laundering
- ISO 20022
- Transaction Monitoring
- Compliance
tools:
- description: Check the operational status of the Tazama fraud detection platform
  hints:
    openWorld: false
    readOnly: true
  name: check-tazama-health
- description: Submit an ISO 20022 pain.001.001.11 customer credit transfer initiation message for real-time fraud detection and AML screening. Returns evaluation results from configured rule processors and typology scoring.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: evaluate-credit-transfer
- description: Submit an ISO 20022 pain.013.001.09 creditor payment activation request for fraud and AML evaluation. Returns rule results and typology scores.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: evaluate-payment-activation
- description: Submit an ISO 20022 pacs.008.001.10 FI-to-FI customer credit transfer for real-time fraud detection. Evaluates the transfer against all active typologies and returns risk assessment results.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: evaluate-interbank-transfer
- description: Submit an ISO 20022 pacs.002.001.12 payment status report for AML compliance evaluation and fraud pattern analysis.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: evaluate-payment-status
---
