---
categories: []
consumed_apis: []
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
- submit a confirmed fraud record
- get fraud alerts
- fraud detection
- lookup transaction
- merchant onboarding risk assessment
- search the match database
- get fraud statuses
- search the match database for terminated merchants
- financial services
- fraud prevention
- match terminated merchant screening
- retrieve ethoca fraud alerts for chargeback prevention
- match
- get available fraud record statuses
- risk management
- update the status of an ethoca fraud alert
- look up transaction details for clarity
- check merchant risk
- submit suspected fraud
- transaction detail lookups for dispute prevention
- update fraud alert
- credit cards
- assess merchant risk during onboarding
- submit a suspected fraud record
- digital identity
- submit a confirmed fraud record to the mastercard fraud and loss database
- open banking
- perform risk check on a merchant
- retrieve ethoca fraud alerts
- mastercard
- ethoca
- ethoca fraud alerts
- search terminated merchants
- look up transaction details to resolve disputes before chargebacks
- search match database
- payments
- suspected fraud record management
- lookup transaction clarity
- confirmed fraud record management
- submit confirmed fraud
slug: fraud-prevention-and-risk
source_filename: fraud-prevention-and-risk.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Fraud Prevention and Risk\n  description: Unified workflow for fraud analysts and risk managers to detect, report, and manage fraud using Mastercard's\n    fraud database, Ethoca alerts, merchant screening (MATCH), and onboarding risk checks.\n  tags:\n  - Mastercard\n  - Fraud Prevention\n  - Risk Management\n  - Ethoca\n  - MATCH\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: confirmed-fraud\n    baseUri: https://api.mastercard.com/fld/confirmed-frauds\n    description: Mastercard Confirmed Fraud API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: mastercard-frauds\n      path: /mastercard-frauds\n      description:\
  \ Confirmed fraud submission for Mastercard transactions\n      operations:\n      - name: submit-mastercard-fraud\n        method: POST\n        description: Add a new fraud record for Mastercard built transactions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fraud: '{{tools.fraud}}'\n      - name: get-fraud-statuses\n        method: GET\n        description: Get available fraud record statuses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: suspected-fraud\n    baseUri: https://api.mastercard.com/fld/suspected-frauds\n    description: Mastercard Suspected Fraud API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name:\
  \ suspected-frauds\n      path: /suspected-frauds\n      description: Suspected fraud management\n      operations:\n      - name: submit-suspected-fraud\n        method: POST\n        description: Submit a suspected fraud record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fraud: '{{tools.fraud}}'\n  - type: http\n    namespace: ethoca-alerts\n    baseUri: https://api.mastercard.com/ethoca/alerts\n    description: Mastercard Ethoca Alerts API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: alerts\n      path: /alerts\n      description: Fraud alert management\n      operations:\n      - name: get-alerts\n        method: GET\n        description: Retrieve fraud alerts\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-alert\n        method: PUT\n        description: Update a fraud alert status\n        inputParameters:\n        - name: alert_id\n          in: path\n          type: string\n          required: true\n          description: Alert identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: ethoca-consumer-clarity\n    baseUri: https://api.mastercard.com/ethoca/consumer-clarity\n    description: Mastercard Ethoca Consumer Clarity API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: transactions\n      path: /transactions\n      description: Transaction clarity lookups\n      operations:\n      - name: lookup-transaction\n        method: POST\n        description: Look up transaction\
  \ details for dispute resolution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transaction: '{{tools.transaction}}'\n  - type: http\n    namespace: ethoca-merchant-services\n    baseUri: https://api.mastercard.com/ethoca/merchant-services\n    description: Mastercard Ethoca Merchant Self Services API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: merchants\n      path: /merchants\n      description: Merchant management for Ethoca\n      operations:\n      - name: get-merchant-profile\n        method: GET\n        description: Retrieve merchant Ethoca profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-merchant-profile\n\
  \        method: PUT\n        description: Update merchant Ethoca preferences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: onboard-risk-check\n    baseUri: https://api.mastercard.com/onboard/risk-check\n    description: Mastercard Onboard Risk Check API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: risk-checks\n      path: /risk-checks\n      description: Merchant risk assessment\n      operations:\n      - name: check-merchant-risk\n        method: POST\n        description: Perform risk assessment on a merchant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchant: '{{tools.merchant}}'\n  - type: http\n  \
  \  namespace: match-pro\n    baseUri: https://api.mastercard.com/fraud/merchant/v3\n    description: Mastercard Match Pro API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: match\n      path: /match\n      description: Terminated merchant screening\n      operations:\n      - name: search-terminated-merchants\n        method: POST\n        description: Search the MATCH database for terminated merchants\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchant: '{{tools.merchant}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: fraud-risk-api\n    description: Unified REST API for Mastercard fraud prevention and risk management.\n    resources:\n    - path: /v1/confirmed-frauds\n      name: confirmed-frauds\n   \
  \   description: Confirmed fraud record management\n      operations:\n      - method: POST\n        name: submit-confirmed-fraud\n        description: Submit a confirmed fraud record\n        call: confirmed-fraud.submit-mastercard-fraud\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/suspected-frauds\n      name: suspected-frauds\n      description: Suspected fraud record management\n      operations:\n      - method: POST\n        name: submit-suspected-fraud\n        description: Submit a suspected fraud record\n        call: suspected-fraud.submit-suspected-fraud\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts\n      name: alerts\n      description: Ethoca fraud alerts\n      operations:\n      - method: GET\n        name: get-fraud-alerts\n        description: Retrieve Ethoca fraud alerts\n        call: ethoca-alerts.get-alerts\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n    - path: /v1/transaction-clarity\n      name: transaction-clarity\n      description: Transaction detail lookups for dispute prevention\n      operations:\n      - method: POST\n        name: lookup-transaction\n        description: Look up transaction details for clarity\n        call: ethoca-consumer-clarity.lookup-transaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/merchant-risk-checks\n      name: merchant-risk-checks\n      description: Merchant onboarding risk assessment\n      operations:\n      - method: POST\n        name: check-merchant-risk\n        description: Perform risk check on a merchant\n        call: onboard-risk-check.check-merchant-risk\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/terminated-merchants\n      name: terminated-merchants\n      description: MATCH terminated merchant screening\n      operations:\n      - method: POST\n        name: search-terminated-merchants\n\
  \        description: Search the MATCH database\n        call: match-pro.search-terminated-merchants\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: fraud-risk-mcp\n    transport: http\n    description: MCP server for AI-assisted fraud prevention and risk management.\n    tools:\n    - name: submit-confirmed-fraud\n      description: Submit a confirmed fraud record to the Mastercard Fraud and Loss Database\n      hints:\n        readOnly: false\n      call: confirmed-fraud.submit-mastercard-fraud\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-suspected-fraud\n      description: Submit a suspected fraud record\n      hints:\n        readOnly: false\n      call: suspected-fraud.submit-suspected-fraud\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fraud-alerts\n      description: Retrieve Ethoca fraud alerts for chargeback prevention\n   \
  \   hints:\n        readOnly: true\n      call: ethoca-alerts.get-alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-fraud-alert\n      description: Update the status of an Ethoca fraud alert\n      hints:\n        readOnly: false\n      call: ethoca-alerts.update-alert\n      with:\n        alert_id: tools.alert_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-transaction-clarity\n      description: Look up transaction details to resolve disputes before chargebacks\n      hints:\n        readOnly: true\n      call: ethoca-consumer-clarity.lookup-transaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-merchant-risk\n      description: Assess merchant risk during onboarding\n      hints:\n        readOnly: true\n      call: onboard-risk-check.check-merchant-risk\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-match-database\n\
  \      description: Search the MATCH database for terminated merchants\n      hints:\n        readOnly: true\n      call: match-pro.search-terminated-merchants\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fraud-statuses\n      description: Get available fraud record statuses\n      hints:\n        readOnly: true\n        idempotent: true\n      call: confirmed-fraud.get-fraud-statuses\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
