---
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
- search the match database for terminated merchants
- financial services
- fraud prevention
- get fraud alerts
- credit cards
- look up transaction details to resolve disputes before chargebacks
- lookup transaction
- search the match database
- confirmed fraud record management
- ethoca
- ethoca fraud alerts
- search terminated merchants
- merchant onboarding risk assessment
- look up transaction details for clarity
- update the status of an ethoca fraud alert
- risk management
- submit a suspected fraud record
- mastercard
- check merchant risk
- suspected fraud record management
- match terminated merchant screening
- match
- submit a confirmed fraud record to the mastercard fraud and loss database
- lookup transaction clarity
- retrieve ethoca fraud alerts
- perform risk check on a merchant
- update fraud alert
- search match database
- digital identity
- payments
- get fraud statuses
- retrieve ethoca fraud alerts for chargeback prevention
- transaction detail lookups for dispute prevention
- assess merchant risk during onboarding
- open banking
- fraud detection
- submit a confirmed fraud record
- submit confirmed fraud
- submit suspected fraud
- get available fraud record statuses
slug: fraud-prevention-and-risk
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
