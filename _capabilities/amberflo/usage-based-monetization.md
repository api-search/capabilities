---
consumed_apis:
- amberflo-metering
- amberflo-billing
description: Unified workflow for API monetization teams combining metering and billing APIs. Enables end-to-end usage tracking, customer management, and billing automation for product and finance teams.
layout: capability
name: Amberflo Usage-Based Monetization
operations:
- description: List all meter definitions
  method: GET
  name: list-meter-definitions
  path: /v1/meter-definitions
- description: Create a new meter definition
  method: POST
  name: create-meter-definition
  path: /v1/meter-definitions
- description: Ingest usage events for metering
  method: POST
  name: ingest-events
  path: /v1/events
- description: Query aggregated usage data
  method: POST
  name: query-usage
  path: /v1/usage
- description: List all customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new customer account
  method: POST
  name: create-customer
  path: /v1/customers
- description: List invoices for a customer
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Create a prepaid order for a customer
  method: POST
  name: create-prepaid-order
  path: /v1/prepaid-orders
personas: []
provider_name: Amberflo
provider_slug: amberflo
search_terms:
- manages pricing models and billing configuration
- ingest meter events to track usage
- finops
- monitors revenue, invoices, and billing analytics
- amberflo
- manage customer accounts
- ai cost management
- ingest events
- create a prepaid credit order for a customer
- ai and cloud cost governance
- manage prepaid credit orders
- list invoices for a specific customer
- usage event tracking and aggregation
- ingest meter events
- create a new meter definition to track usage events
- manage meter definitions for tracking usage
- API Developer
- query usage data
- list all customer accounts in amberflo
- usage-based billing
- monetization
- create a new customer account in amberflo
- create meter definition
- create a new customer account
- create prepaid order
- ingest usage events for metering
- integrates metering sdk and ingests usage events
- list all meter definitions for usage tracking
- list all customers
- retrieve customer invoices
- Finance Team
- Product Manager
- metering
- query aggregated usage data
- query usage
- list meter definitions
- list all meter definitions
- customer billing and subscription management
- create a new meter definition
- list invoices
- query aggregated usage data for a meter
- create customer
- create a prepaid order for a customer
- billing
- list invoices for a customer
- list customers
- end-to-end workflow combining metering and billing apis
slug: usage-based-monetization
tags:
- Amberflo
- Usage-Based Billing
- Metering
- Monetization
- FinOps
tools:
- description: List all meter definitions for usage tracking
  hints:
    openWorld: true
    readOnly: true
  name: list-meter-definitions
- description: Create a new meter definition to track usage events
  hints:
    readOnly: false
  name: create-meter-definition
- description: Ingest meter events to track usage
  hints:
    readOnly: false
  name: ingest-events
- description: Query aggregated usage data for a meter
  hints:
    openWorld: true
    readOnly: true
  name: query-usage
- description: List all customer accounts in Amberflo
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Create a new customer account in Amberflo
  hints:
    readOnly: false
  name: create-customer
- description: List invoices for a specific customer
  hints:
    openWorld: true
    readOnly: true
  name: list-invoices
- description: Create a prepaid credit order for a customer
  hints:
    readOnly: false
  name: create-prepaid-order
---
