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
- get dispute defense reasons
- list stores
- get applicable defense reasons for a chargeback dispute.
- list all merchant accounts.
- builds payment integrations using adyen apis and sdks.
- accept a dispute.
- accept chargeback dispute
- management
- manages merchant accounts, terminals, and dispute responses.
- submit a defense document.
- accept dispute
- get defense reasons
- online and in-person payment acceptance.
- get dispute defense reasons.
- marketplace and platform fund management.
- supply dispute defense document
- 'unified capability for accepting and managing online payments. combines the checkout api and payments api to provide merchants and developers with a complete payment acceptance workflow including session creation, payment authorisation, refunds, and cancellations. primary persona: developer or merchant platform engineer.'
- merchants
- list payment method settings
- accept a chargeback dispute.
- get details of a specific merchant account.
- operations
- get merchant
- manage merchant stores.
- manage merchant accounts.
- list terminals for a merchant.
- list all adyen merchant accounts.
- financial services
- retrieve defense reasons for a dispute.
- adyen
- builds marketplace and fintech platforms using adyen balance platform.
- list all stores for a merchant account.
- submit a defense document for a chargeback dispute.
- 'unified capability for building financial products on adyen''s balance platform. combines the configuration api for account holder and card management with the transfers api for fund movement. used by marketplace and platform builders to onboard users, issue cards, and manage fund transfers. primary persona: platform engineer or marketplace developer.'
- list terminals
- list stores for a merchant.
- list merchants
- 'unified capability for managing adyen merchant accounts, stores, payment terminals, and dispute resolution. combines management api and disputes api to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. primary persona: merchant operations team or platform administrator.'
- fintech
- list all payment terminals for a merchant account.
- manage payment terminals.
- accept a chargeback dispute and let it proceed.
- payments
- disputes
- merchant account and balance platform configuration.
- chargeback and dispute handling.
- submit dispute defense documents.
- list payment method settings for a merchant.
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
