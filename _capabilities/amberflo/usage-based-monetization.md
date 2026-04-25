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
- end-to-end workflow combining metering and billing apis
- list invoices for a customer
- create a prepaid order for a customer
- integrates metering sdk and ingests usage events
- create prepaid order
- query aggregated usage data
- ingest meter events to track usage
- create a new customer account
- list all meter definitions for usage tracking
- retrieve customer invoices
- manage meter definitions for tracking usage
- usage-based billing
- list customers
- manages pricing models and billing configuration
- create a prepaid credit order for a customer
- ingest meter events
- ai cost management
- query usage
- Finance Team
- finops
- query usage data
- metering
- list all customer accounts in amberflo
- list invoices for a specific customer
- list all customers
- list all meter definitions
- usage event tracking and aggregation
- list meter definitions
- create a new meter definition to track usage events
- amberflo
- query aggregated usage data for a meter
- ingest events
- monitors revenue, invoices, and billing analytics
- create meter definition
- create customer
- Product Manager
- ingest usage events for metering
- billing
- customer billing and subscription management
- create a new customer account in amberflo
- list invoices
- manage prepaid credit orders
- create a new meter definition
- ai and cloud cost governance
- API Developer
- manage customer accounts
- monetization
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
