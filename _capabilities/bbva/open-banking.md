---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Open Banking
operations: []
personas: []
provider_name: BBVA
provider_slug: bbva
search_terms:
- financial services
- mexico
- banking
- psd2
- open banking
- spain
slug: open-banking
source_yaml: "capability:\n  name: BBVA Open Banking\n  description: >-\n    BBVA's open banking capabilities provide PSD2-compliant account information and\n    payment initiation services for Spain and EU markets, alongside multi-country\n    treasury management, business payments, and collections APIs across 15+ countries.\n  categories:\n    - name: Account Information (AIS)\n      description: PSD2 Account Information Services for accessing customer account data with consent.\n      operations:\n        - name: List Accounts\n          description: Retrieve list of customer payment accounts.\n        - name: Get Account Details\n          description: Retrieve details for a specific payment account.\n        - name: Get Account Balances\n          description: Retrieve current and available balances for an account.\n        - name: Get Account Transactions\n          description: Retrieve transaction history for an account within a date range.\n    - name: Payment Initiation (PIS)\n\
  \      description: PSD2 Payment Initiation Services for initiating payments with customer consent.\n      operations:\n        - name: Initiate SEPA Credit Transfer\n          description: Initiate a SEPA credit transfer payment.\n        - name: Initiate Instant Payment\n          description: Initiate a SEPA Instant Credit Transfer (SCT Inst).\n        - name: Get Payment Status\n          description: Check the status of a previously initiated payment.\n        - name: Cancel Payment\n          description: Cancel a payment that has not yet been executed.\n    - name: Business Payments\n      description: Treasury and corporate payment services for business customers.\n      operations:\n        - name: Bulk Payment Initiation\n          description: Submit bulk payment files for payroll or supplier disbursements.\n        - name: SPEI Transfer (Mexico)\n          description: Initiate interbank transfers via Mexico's SPEI system.\n    - name: Open Data\n      description: Publicly\
  \ accessible data APIs without authentication.\n      operations:\n        - name: Get Branch Locations\n          description: Retrieve BBVA branch locations with address, hours, and services.\n        - name: Get ATM Locations\n          description: Retrieve BBVA ATM locations with coordinates and availability.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bbva/refs/heads/main/capabilities/open-banking.yaml
tags: []
tools: []
---
