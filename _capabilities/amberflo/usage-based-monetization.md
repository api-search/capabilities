---
categories: []
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
- ingest events
- query usage data
- query usage
- list invoices for a specific customer
- ai cost management
- list all meter definitions for usage tracking
- API Developer
- Finance Team
- monetization
- manages pricing models and billing configuration
- usage-based billing
- metering
- query aggregated usage data for a meter
- create prepaid order
- list all meter definitions
- manage prepaid credit orders
- create a prepaid order for a customer
- monitors revenue, invoices, and billing analytics
- list customers
- usage event tracking and aggregation
- list invoices for a customer
- end-to-end workflow combining metering and billing apis
- finops
- ingest meter events
- retrieve customer invoices
- customer billing and subscription management
- list all customer accounts in amberflo
- billing
- amberflo
- list all customers
- create a new customer account in amberflo
- list meter definitions
- create a prepaid credit order for a customer
- create a new meter definition
- integrates metering sdk and ingests usage events
- query aggregated usage data
- ai and cloud cost governance
- manage customer accounts
- create a new customer account
- create customer
- create a new meter definition to track usage events
- ingest meter events to track usage
- create meter definition
- list invoices
- Product Manager
- ingest usage events for metering
- manage meter definitions for tracking usage
slug: usage-based-monetization
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amberflo Usage-Based Monetization\n  description: >-\n    Unified workflow for API monetization teams combining metering and billing APIs.\n    Enables end-to-end usage tracking, customer management, and billing automation\n    for product and finance teams.\n  tags:\n    - Amberflo\n    - Usage-Based Billing\n    - Metering\n    - Monetization\n    - FinOps\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMBERFLO_API_KEY: AMBERFLO_API_KEY\n\ncapability:\n  consumes:\n    - import: amberflo-metering\n      location: ./shared/metering-api.yaml\n    - import: amberflo-billing\n      location: ./shared/billing-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: amberflo-monetization-api\n      description: Unified REST API for usage-based monetization workflows.\n      resources:\n        - path: /v1/meter-definitions\n          name: meter-definitions\n\
  \          description: Manage meter definitions for tracking usage\n          operations:\n            - method: GET\n              name: list-meter-definitions\n              description: List all meter definitions\n              call: \"amberflo-metering.list-meter-definitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-meter-definition\n              description: Create a new meter definition\n              call: \"amberflo-metering.create-meter-definition\"\n              with:\n                meterApiName: \"rest.meterApiName\"\n                displayName: \"rest.displayName\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: Ingest meter events\n          operations:\n            - method: POST\n        \
  \      name: ingest-events\n              description: Ingest usage events for metering\n              call: \"amberflo-metering.ingest-meter-events\"\n              with:\n                meterApiName: \"rest.meterApiName\"\n                customerId: \"rest.customerId\"\n                meterValue: \"rest.meterValue\"\n                meterTimeInMillis: \"rest.meterTimeInMillis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/usage\n          name: usage\n          description: Query usage data\n          operations:\n            - method: POST\n              name: query-usage\n              description: Query aggregated usage data\n              call: \"amberflo-metering.query-usage\"\n              with:\n                meterApiName: \"rest.meterApiName\"\n                startTimeInSeconds: \"rest.startTimeInSeconds\"\n                endTimeInSeconds: \"rest.endTimeInSeconds\"\n                aggregation:\
  \ \"rest.aggregation\"\n                timeGroupingInterval: \"rest.timeGroupingInterval\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers\n          name: customers\n          description: Manage customer accounts\n          operations:\n            - method: GET\n              name: list-customers\n              description: List all customers\n              call: \"amberflo-billing.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: Create a new customer account\n              call: \"amberflo-billing.create-customer\"\n              with:\n                customerId: \"rest.customerId\"\n                customerName: \"rest.customerName\"\n                customerEmail: \"rest.customerEmail\"\n                lifecycleStage: \"rest.lifecycleStage\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices\n          name: invoices\n          description: Retrieve customer invoices\n          operations:\n            - method: GET\n              name: list-invoices\n              description: List invoices for a customer\n              call: \"amberflo-billing.list-invoices\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/prepaid-orders\n          name: prepaid-orders\n          description: Manage prepaid credit orders\n          operations:\n            - method: POST\n              name: create-prepaid-order\n              description: Create a prepaid order for a customer\n              call: \"amberflo-billing.create-prepaid-order\"\n              with:\n                customerId: \"rest.customerId\"\n         \
  \       amount: \"rest.amount\"\n                currency: \"rest.currency\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: amberflo-monetization-mcp\n      transport: http\n      description: MCP server for AI-assisted usage-based monetization and billing automation.\n      tools:\n        - name: list-meter-definitions\n          description: List all meter definitions for usage tracking\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amberflo-metering.list-meter-definitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-meter-definition\n          description: Create a new meter definition to track usage events\n          hints:\n            readOnly: false\n          call: \"amberflo-metering.create-meter-definition\"\n          with:\n            meterApiName: \"\
  tools.meterApiName\"\n            displayName: \"tools.displayName\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ingest-events\n          description: Ingest meter events to track usage\n          hints:\n            readOnly: false\n          call: \"amberflo-metering.ingest-meter-events\"\n          with:\n            meterApiName: \"tools.meterApiName\"\n            customerId: \"tools.customerId\"\n            meterValue: \"tools.meterValue\"\n            meterTimeInMillis: \"tools.meterTimeInMillis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-usage\n          description: Query aggregated usage data for a meter\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amberflo-metering.query-usage\"\n          with:\n            meterApiName: \"tools.meterApiName\"\n            startTimeInSeconds:\
  \ \"tools.startTimeInSeconds\"\n            endTimeInSeconds: \"tools.endTimeInSeconds\"\n            aggregation: \"tools.aggregation\"\n            timeGroupingInterval: \"tools.timeGroupingInterval\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-customers\n          description: List all customer accounts in Amberflo\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amberflo-billing.list-customers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: Create a new customer account in Amberflo\n          hints:\n            readOnly: false\n          call: \"amberflo-billing.create-customer\"\n          with:\n            customerId: \"tools.customerId\"\n            customerName: \"tools.customerName\"\n            customerEmail: \"tools.customerEmail\"\n            lifecycleStage: \"tools.lifecycleStage\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-invoices\n          description: List invoices for a specific customer\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amberflo-billing.list-invoices\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-prepaid-order\n          description: Create a prepaid credit order for a customer\n          hints:\n            readOnly: false\n          call: \"amberflo-billing.create-prepaid-order\"\n          with:\n            customerId: \"tools.customerId\"\n            amount: \"tools.amount\"\n            currency: \"tools.currency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amberflo/refs/heads/main/capabilities/usage-based-monetization.yaml
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
