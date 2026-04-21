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
- list customers
- create a new customer account in amberflo
- create a prepaid credit order for a customer
- ingest events
- metering
- monitors revenue, invoices, and billing analytics
- manage meter definitions for tracking usage
- create prepaid order
- Product Manager
- ingest meter events
- query aggregated usage data for a meter
- manage prepaid credit orders
- list invoices for a specific customer
- usage event tracking and aggregation
- monetization
- usage-based billing
- list all customers
- create customer
- create a prepaid order for a customer
- ingest meter events to track usage
- list all customer accounts in amberflo
- billing
- query aggregated usage data
- finops
- customer billing and subscription management
- amberflo
- end-to-end workflow combining metering and billing apis
- list invoices
- list invoices for a customer
- integrates metering sdk and ingests usage events
- query usage
- query usage data
- ingest usage events for metering
- ai cost management
- list meter definitions
- Finance Team
- API Developer
- retrieve customer invoices
- ai and cloud cost governance
- manage customer accounts
- create meter definition
- manages pricing models and billing configuration
- list all meter definitions for usage tracking
- list all meter definitions
- create a new meter definition
- create a new customer account
- create a new meter definition to track usage events
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
