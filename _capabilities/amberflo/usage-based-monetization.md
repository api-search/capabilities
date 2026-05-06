---
categories: []
consumed_apis: []
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
- list invoices for a customer
- list invoices for a specific customer
- ingest usage events for metering
- create prepaid order
- usage-based billing
- create meter definition
- amberflo
- finops
- query aggregated usage data for a meter
- create a prepaid order for a customer
- ingest events
- create a new meter definition to track usage events
- end-to-end workflow combining metering and billing apis
- ai cost management
- list all meter definitions for usage tracking
- query usage
- ingest meter events to track usage
- Finance Team
- billing
- API Developer
- manages pricing models and billing configuration
- create a new meter definition
- create a new customer account in amberflo
- Product Manager
- manage meter definitions for tracking usage
- monetization
- usage event tracking and aggregation
- query aggregated usage data
- metering
- list meter definitions
- list all meter definitions
- integrates metering sdk and ingests usage events
- create customer
- list all customers
- customer billing and subscription management
- list customers
- create a new customer account
- ingest meter events
- manage customer accounts
- retrieve customer invoices
- create a prepaid credit order for a customer
- monitors revenue, invoices, and billing analytics
- list invoices
- manage prepaid credit orders
- ai and cloud cost governance
- list all customer accounts in amberflo
- query usage data
slug: usage-based-monetization
source_filename: usage-based-monetization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amberflo Usage-Based Monetization\n  description: Unified workflow for API monetization teams combining metering and billing APIs. Enables end-to-end usage tracking,\n    customer management, and billing automation for product and finance teams.\n  tags:\n  - Amberflo\n  - Usage-Based Billing\n  - Metering\n  - Monetization\n  - FinOps\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMBERFLO_API_KEY: AMBERFLO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amberflo-metering\n    baseUri: https://app.amberflo.io\n    description: Amberflo Metering API for event ingestion and usage queries.\n    authentication:\n      type: apikey\n      key: X-API-KEY\n      value: '{{AMBERFLO_API_KEY}}'\n      placement: header\n    resources:\n    - name: meter-definitions\n      path: /meter-definition\n      description: Meter definition management\n      operations:\n      - name: list-meter-definitions\n\
  \        method: GET\n        description: List all meter definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-meter-definition\n        method: POST\n        description: Create a new meter definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            meterApiName: '{{tools.meterApiName}}'\n            displayName: '{{tools.displayName}}'\n            type: '{{tools.type}}'\n      - name: update-meter-definition\n        method: PUT\n        description: Update an existing meter definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-ingestion\n      path: /ingest\n      description: Meter event ingestion endpoint\n      operations:\n    \
  \  - name: ingest-meter-events\n        method: POST\n        description: Ingest one or more meter events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            meterApiName: '{{tools.meterApiName}}'\n            customerId: '{{tools.customerId}}'\n            meterValue: '{{tools.meterValue}}'\n            meterTimeInMillis: '{{tools.meterTimeInMillis}}'\n    - name: usage-queries\n      path: /usage\n      description: Usage data query endpoint\n      operations:\n      - name: query-usage\n        method: POST\n        description: Query aggregated usage data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            meterApiName: '{{tools.meterApiName}}'\n            startTimeInSeconds: '{{tools.startTimeInSeconds}}'\n\
  \            endTimeInSeconds: '{{tools.endTimeInSeconds}}'\n            aggregation: '{{tools.aggregation}}'\n            timeGroupingInterval: '{{tools.timeGroupingInterval}}'\n  - type: http\n    namespace: amberflo-billing\n    baseUri: https://app.amberflo.io\n    description: Amberflo Billing API for customer and subscription management.\n    authentication:\n      type: apikey\n      key: X-API-KEY\n      value: '{{AMBERFLO_API_KEY}}'\n      placement: header\n    resources:\n    - name: customers\n      path: /customers\n      description: Customer account management\n      operations:\n      - name: list-customers\n        method: GET\n        description: List all customers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create a new customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n            customerName: '{{tools.customerName}}'\n            customerEmail: '{{tools.customerEmail}}'\n            lifecycleStage: '{{tools.lifecycleStage}}'\n      - name: update-customer\n        method: PUT\n        description: Update an existing customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /payments-billing-customer-product-invoice\n      description: Customer invoice management\n      operations:\n      - name: list-invoices\n        method: GET\n        description: List invoices for a customer\n        inputParameters:\n        - name: customerId\n          in: query\n          type: string\n          required: true\n          description: Customer ID to list invoices for\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prepaid-orders\n      path: /payments-pricing-amberflo-customer-prepaid\n      description: Prepaid credit order management\n      operations:\n      - name: create-prepaid-order\n        method: POST\n        description: Create a prepaid order for a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amberflo-monetization-api\n    description: Unified REST API for usage-based monetization workflows.\n    resources:\n    - path: /v1/meter-definitions\n      name: meter-definitions\n      description: Manage meter definitions for tracking usage\n      operations:\n\
  \      - method: GET\n        name: list-meter-definitions\n        description: List all meter definitions\n        call: amberflo-metering.list-meter-definitions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-meter-definition\n        description: Create a new meter definition\n        call: amberflo-metering.create-meter-definition\n        with:\n          meterApiName: rest.meterApiName\n          displayName: rest.displayName\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Ingest meter events\n      operations:\n      - method: POST\n        name: ingest-events\n        description: Ingest usage events for metering\n        call: amberflo-metering.ingest-meter-events\n        with:\n          meterApiName: rest.meterApiName\n          customerId: rest.customerId\n          meterValue: rest.meterValue\n\
  \          meterTimeInMillis: rest.meterTimeInMillis\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/usage\n      name: usage\n      description: Query usage data\n      operations:\n      - method: POST\n        name: query-usage\n        description: Query aggregated usage data\n        call: amberflo-metering.query-usage\n        with:\n          meterApiName: rest.meterApiName\n          startTimeInSeconds: rest.startTimeInSeconds\n          endTimeInSeconds: rest.endTimeInSeconds\n          aggregation: rest.aggregation\n          timeGroupingInterval: rest.timeGroupingInterval\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Manage customer accounts\n      operations:\n      - method: GET\n        name: list-customers\n        description: List all customers\n        call: amberflo-billing.list-customers\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Create a new customer account\n        call: amberflo-billing.create-customer\n        with:\n          customerId: rest.customerId\n          customerName: rest.customerName\n          customerEmail: rest.customerEmail\n          lifecycleStage: rest.lifecycleStage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Retrieve customer invoices\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List invoices for a customer\n        call: amberflo-billing.list-invoices\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/prepaid-orders\n      name: prepaid-orders\n      description: Manage prepaid credit orders\n      operations:\n      - method: POST\n        name:\
  \ create-prepaid-order\n        description: Create a prepaid order for a customer\n        call: amberflo-billing.create-prepaid-order\n        with:\n          customerId: rest.customerId\n          amount: rest.amount\n          currency: rest.currency\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amberflo-monetization-mcp\n    transport: http\n    description: MCP server for AI-assisted usage-based monetization and billing automation.\n    tools:\n    - name: list-meter-definitions\n      description: List all meter definitions for usage tracking\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amberflo-metering.list-meter-definitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-meter-definition\n      description: Create a new meter definition to track usage events\n      hints:\n        readOnly: false\n      call: amberflo-metering.create-meter-definition\n\
  \      with:\n        meterApiName: tools.meterApiName\n        displayName: tools.displayName\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ingest-events\n      description: Ingest meter events to track usage\n      hints:\n        readOnly: false\n      call: amberflo-metering.ingest-meter-events\n      with:\n        meterApiName: tools.meterApiName\n        customerId: tools.customerId\n        meterValue: tools.meterValue\n        meterTimeInMillis: tools.meterTimeInMillis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-usage\n      description: Query aggregated usage data for a meter\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amberflo-metering.query-usage\n      with:\n        meterApiName: tools.meterApiName\n        startTimeInSeconds: tools.startTimeInSeconds\n        endTimeInSeconds: tools.endTimeInSeconds\n        aggregation: tools.aggregation\n\
  \        timeGroupingInterval: tools.timeGroupingInterval\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customers\n      description: List all customer accounts in Amberflo\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amberflo-billing.list-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Create a new customer account in Amberflo\n      hints:\n        readOnly: false\n      call: amberflo-billing.create-customer\n      with:\n        customerId: tools.customerId\n        customerName: tools.customerName\n        customerEmail: tools.customerEmail\n        lifecycleStage: tools.lifecycleStage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: List invoices for a specific customer\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amberflo-billing.list-invoices\n\
  \      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-prepaid-order\n      description: Create a prepaid credit order for a customer\n      hints:\n        readOnly: false\n      call: amberflo-billing.create-prepaid-order\n      with:\n        customerId: tools.customerId\n        amount: tools.amount\n        currency: tools.currency\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
