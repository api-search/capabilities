---
categories: []
consumed_apis:
- confirmed-fraud
- suspected-fraud
- ethoca-alerts
- ethoca-consumer-clarity
- ethoca-merchant-services
- onboard-risk-check
- match-pro
description: Unified workflow for fraud analysts and risk managers to detect, report, and manage fraud using Mastercard's fraud database, Ethoca alerts, merchant screening (MATCH), and onboarding risk checks.
layout: capability
name: Mastercard Fraud Prevention and Risk
operations:
- description: Submit a confirmed fraud record
  method: POST
  name: submit-confirmed-fraud
  path: /v1/confirmed-frauds
- description: Submit a suspected fraud record
  method: POST
  name: submit-suspected-fraud
  path: /v1/suspected-frauds
- description: Retrieve Ethoca fraud alerts
  method: GET
  name: get-fraud-alerts
  path: /v1/alerts
- description: Look up transaction details for clarity
  method: POST
  name: lookup-transaction
  path: /v1/transaction-clarity
- description: Perform risk check on a merchant
  method: POST
  name: check-merchant-risk
  path: /v1/merchant-risk-checks
- description: Search the MATCH database
  method: POST
  name: search-terminated-merchants
  path: /v1/terminated-merchants
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- submit a suspected fraud record
- check merchant risk
- submit confirmed fraud
- open banking
- financial services
- match terminated merchant screening
- mastercard
- retrieve ethoca fraud alerts
- transaction detail lookups for dispute prevention
- look up transaction details to resolve disputes before chargebacks
- submit a confirmed fraud record
- search match database
- search the match database for terminated merchants
- payments
- submit a confirmed fraud record to the mastercard fraud and loss database
- risk management
- retrieve ethoca fraud alerts for chargeback prevention
- lookup transaction
- fraud prevention
- merchant onboarding risk assessment
- confirmed fraud record management
- perform risk check on a merchant
- fraud detection
- search terminated merchants
- ethoca
- credit cards
- search the match database
- ethoca fraud alerts
- submit suspected fraud
- match
- assess merchant risk during onboarding
- get available fraud record statuses
- digital identity
- get fraud alerts
- update fraud alert
- update the status of an ethoca fraud alert
- lookup transaction clarity
- get fraud statuses
- look up transaction details for clarity
- suspected fraud record management
slug: fraud-prevention-and-risk
source_filename: fraud-prevention-and-risk.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Mastercard Fraud Prevention and Risk\"\n  description: \"Unified workflow for fraud analysts and risk managers to detect, report, and manage fraud using Mastercard's fraud database, Ethoca alerts, merchant screening (MATCH), and onboarding risk checks.\"\n  tags:\n    - Mastercard\n    - Fraud Prevention\n    - Risk Management\n    - Ethoca\n    - MATCH\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n      MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\n\ncapability:\n  consumes:\n    - import: confirmed-fraud\n      location: ./shared/confirmed-fraud.yaml\n    - import: suspected-fraud\n      location: ./shared/suspected-fraud.yaml\n    - import: ethoca-alerts\n      location: ./shared/ethoca-alerts.yaml\n    - import: ethoca-consumer-clarity\n      location: ./shared/ethoca-consumer-clarity.yaml\n    - import: ethoca-merchant-services\n\
  \      location: ./shared/ethoca-merchant-self-services.yaml\n    - import: onboard-risk-check\n      location: ./shared/onboard-risk-check.yaml\n    - import: match-pro\n      location: ./shared/match-pro.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: fraud-risk-api\n      description: \"Unified REST API for Mastercard fraud prevention and risk management.\"\n      resources:\n        - path: /v1/confirmed-frauds\n          name: confirmed-frauds\n          description: \"Confirmed fraud record management\"\n          operations:\n            - method: POST\n              name: submit-confirmed-fraud\n              description: \"Submit a confirmed fraud record\"\n              call: \"confirmed-fraud.submit-mastercard-fraud\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/suspected-frauds\n          name: suspected-frauds\n          description: \"Suspected fraud record management\"\n\
  \          operations:\n            - method: POST\n              name: submit-suspected-fraud\n              description: \"Submit a suspected fraud record\"\n              call: \"suspected-fraud.submit-suspected-fraud\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/alerts\n          name: alerts\n          description: \"Ethoca fraud alerts\"\n          operations:\n            - method: GET\n              name: get-fraud-alerts\n              description: \"Retrieve Ethoca fraud alerts\"\n              call: \"ethoca-alerts.get-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transaction-clarity\n          name: transaction-clarity\n          description: \"Transaction detail lookups for dispute prevention\"\n          operations:\n            - method: POST\n              name: lookup-transaction\n              description: \"\
  Look up transaction details for clarity\"\n              call: \"ethoca-consumer-clarity.lookup-transaction\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/merchant-risk-checks\n          name: merchant-risk-checks\n          description: \"Merchant onboarding risk assessment\"\n          operations:\n            - method: POST\n              name: check-merchant-risk\n              description: \"Perform risk check on a merchant\"\n              call: \"onboard-risk-check.check-merchant-risk\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/terminated-merchants\n          name: terminated-merchants\n          description: \"MATCH terminated merchant screening\"\n          operations:\n            - method: POST\n              name: search-terminated-merchants\n              description: \"Search the MATCH database\"\n              call: \"\
  match-pro.search-terminated-merchants\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: fraud-risk-mcp\n      transport: http\n      description: \"MCP server for AI-assisted fraud prevention and risk management.\"\n      tools:\n        - name: submit-confirmed-fraud\n          description: \"Submit a confirmed fraud record to the Mastercard Fraud and Loss Database\"\n          hints:\n            readOnly: false\n          call: \"confirmed-fraud.submit-mastercard-fraud\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-suspected-fraud\n          description: \"Submit a suspected fraud record\"\n          hints:\n            readOnly: false\n          call: \"suspected-fraud.submit-suspected-fraud\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-fraud-alerts\n\
  \          description: \"Retrieve Ethoca fraud alerts for chargeback prevention\"\n          hints:\n            readOnly: true\n          call: \"ethoca-alerts.get-alerts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-fraud-alert\n          description: \"Update the status of an Ethoca fraud alert\"\n          hints:\n            readOnly: false\n          call: \"ethoca-alerts.update-alert\"\n          with:\n            alert_id: \"tools.alert_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-transaction-clarity\n          description: \"Look up transaction details to resolve disputes before chargebacks\"\n          hints:\n            readOnly: true\n          call: \"ethoca-consumer-clarity.lookup-transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-merchant-risk\n          description:\
  \ \"Assess merchant risk during onboarding\"\n          hints:\n            readOnly: true\n          call: \"onboard-risk-check.check-merchant-risk\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-match-database\n          description: \"Search the MATCH database for terminated merchants\"\n          hints:\n            readOnly: true\n          call: \"match-pro.search-terminated-merchants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-fraud-statuses\n          description: \"Get available fraud record statuses\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"confirmed-fraud.get-fraud-statuses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/fraud-prevention-and-risk.yaml
tags:
- Mastercard
- Fraud Prevention
- Risk Management
- Ethoca
- MATCH
tools:
- description: Submit a confirmed fraud record to the Mastercard Fraud and Loss Database
  hints:
    readOnly: false
  name: submit-confirmed-fraud
- description: Submit a suspected fraud record
  hints:
    readOnly: false
  name: submit-suspected-fraud
- description: Retrieve Ethoca fraud alerts for chargeback prevention
  hints:
    readOnly: true
  name: get-fraud-alerts
- description: Update the status of an Ethoca fraud alert
  hints:
    readOnly: false
  name: update-fraud-alert
- description: Look up transaction details to resolve disputes before chargebacks
  hints:
    readOnly: true
  name: lookup-transaction-clarity
- description: Assess merchant risk during onboarding
  hints:
    readOnly: true
  name: check-merchant-risk
- description: Search the MATCH database for terminated merchants
  hints:
    readOnly: true
  name: search-match-database
- description: Get available fraud record statuses
  hints:
    idempotent: true
    readOnly: true
  name: get-fraud-statuses
---
