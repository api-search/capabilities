---
consumed_apis:
- management
- disputes
description: 'Unified capability for managing Adyen merchant accounts, stores, payment terminals, and dispute resolution. Combines Management API and Disputes API to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. Primary persona: Merchant Operations Team or Platform Administrator.'
layout: capability
name: Adyen Merchant Account Management
operations:
- description: List all merchant accounts.
  method: GET
  name: list-merchants
  path: /v1/merchants
- description: List stores for a merchant.
  method: GET
  name: list-stores
  path: /v1/merchants/{merchantId}/stores
- description: List terminals for a merchant.
  method: GET
  name: list-terminals
  path: /v1/merchants/{merchantId}/terminals
- description: Retrieve defense reasons for a dispute.
  method: POST
  name: get-defense-reasons
  path: /v1/disputes/defense-reasons
- description: Submit a defense document.
  method: POST
  name: supply-defense-document
  path: /v1/disputes/documents
- description: Accept a chargeback dispute.
  method: POST
  name: accept-dispute
  path: /v1/disputes/accept
personas: []
provider_name: Adyen
provider_slug: adyen
search_terms:
- supply defense document
- accept a dispute.
- list all stores for a merchant account.
- 'unified capability for accepting and managing online payments. combines the checkout api and payments api to provide merchants and developers with a complete payment acceptance workflow including session creation, payment authorisation, refunds, and cancellations. primary persona: developer or merchant platform engineer.'
- list merchants
- financial services
- list stores for a merchant.
- manage payment terminals.
- list terminals for a merchant.
- submit a defense document.
- list stores
- manage merchant stores.
- manage merchant accounts.
- merchants
- get dispute defense reasons.
- 'unified capability for building financial products on adyen''s balance platform. combines the configuration api for account holder and card management with the transfers api for fund movement. used by marketplace and platform builders to onboard users, issue cards, and manage fund transfers. primary persona: platform engineer or marketplace developer.'
- accept a chargeback dispute.
- merchant account and balance platform configuration.
- get applicable defense reasons for a chargeback dispute.
- marketplace and platform fund management.
- retrieve defense reasons for a dispute.
- get details of a specific merchant account.
- fintech
- management
- operations
- accept chargeback dispute
- 'unified capability for managing adyen merchant accounts, stores, payment terminals, and dispute resolution. combines management api and disputes api to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. primary persona: merchant operations team or platform administrator.'
- supply dispute defense document
- get defense reasons
- list payment method settings for a merchant.
- submit a defense document for a chargeback dispute.
- accept dispute
- get dispute defense reasons
- list all payment terminals for a merchant account.
- list all merchant accounts.
- submit dispute defense documents.
- accept a chargeback dispute and let it proceed.
- builds marketplace and fintech platforms using adyen balance platform.
- adyen
- disputes
- list payment method settings
- payments
- list terminals
- list all adyen merchant accounts.
- builds payment integrations using adyen apis and sdks.
- chargeback and dispute handling.
- online and in-person payment acceptance.
- manages merchant accounts, terminals, and dispute responses.
- get merchant
slug: merchant-account-management
tags:
- Adyen
- Management
- Merchants
- Disputes
- Operations
tools:
- description: List all Adyen merchant accounts.
  hints:
    destructive: false
    readOnly: true
  name: list-merchants
- description: Get details of a specific merchant account.
  hints:
    destructive: false
    readOnly: true
  name: get-merchant
- description: List all stores for a merchant account.
  hints:
    destructive: false
    readOnly: true
  name: list-stores
- description: List all payment terminals for a merchant account.
  hints:
    destructive: false
    readOnly: true
  name: list-terminals
- description: List payment method settings for a merchant.
  hints:
    destructive: false
    readOnly: true
  name: list-payment-method-settings
- description: Get applicable defense reasons for a chargeback dispute.
  hints:
    destructive: false
    readOnly: true
  name: get-dispute-defense-reasons
- description: Submit a defense document for a chargeback dispute.
  hints:
    destructive: false
    readOnly: false
  name: supply-dispute-defense-document
- description: Accept a chargeback dispute and let it proceed.
  hints:
    destructive: true
    readOnly: false
  name: accept-chargeback-dispute
---
