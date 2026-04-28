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
- search the match database for terminated merchants
- get available fraud record statuses
- get fraud statuses
- ethoca fraud alerts
- ethoca
- credit cards
- fraud prevention
- submit confirmed fraud
- search terminated merchants
- confirmed fraud record management
- submit a confirmed fraud record
- transaction detail lookups for dispute prevention
- digital identity
- match
- match terminated merchant screening
- update fraud alert
- open banking
- retrieve ethoca fraud alerts for chargeback prevention
- update the status of an ethoca fraud alert
- retrieve ethoca fraud alerts
- check merchant risk
- submit a confirmed fraud record to the mastercard fraud and loss database
- look up transaction details to resolve disputes before chargebacks
- risk management
- merchant onboarding risk assessment
- mastercard
- fraud detection
- lookup transaction clarity
- look up transaction details for clarity
- get fraud alerts
- perform risk check on a merchant
- suspected fraud record management
- financial services
- search the match database
- payments
- lookup transaction
- submit suspected fraud
- assess merchant risk during onboarding
- search match database
- submit a suspected fraud record
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
