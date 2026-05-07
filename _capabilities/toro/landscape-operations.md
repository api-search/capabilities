---
categories: []
consumed_apis: []
description: Unified workflow capability for landscape contractors combining Horizon360 business management with IntelliDash irrigation and fleet monitoring. Enables end-to-end operations from customer management and job scheduling through crew dispatch, equipment tracking, and invoicing.
layout: capability
name: Toro Landscape Operations
operations:
- description: List all customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get a customer by ID
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
- description: List landscaping jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Create a new landscaping job
  method: POST
  name: create-job
  path: /v1/jobs
- description: List job schedules
  method: GET
  name: list-schedules
  path: /v1/schedules
- description: Schedule a job for a crew
  method: POST
  name: create-schedule-entry
  path: /v1/schedules
- description: List all crews
  method: GET
  name: list-crews
  path: /v1/crews
- description: List invoices
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Create a new invoice
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: List landscaping equipment
  method: GET
  name: list-equipment
  path: /v1/equipment
- description: List payments
  method: GET
  name: list-payments
  path: /v1/payments
- description: Process a payment
  method: POST
  name: process-payment
  path: /v1/payments
personas: []
provider_name: Toro
provider_slug: toro
search_terms:
- operations
- create customer
- create job
- crew and job scheduling
- list landscaping jobs
- landscaping
- invoice management
- list equipment
- create a new invoice for a customer or completed job
- list all landscaping equipment in the fleet
- irrigation
- create a new invoice
- create a new customer record for a landscape contractor
- crew management
- create a new landscaping job for a customer
- list landscaping equipment
- create a new landscaping job
- business management
- schedule job
- individual customer management
- process a customer payment for an invoice
- get a customer by id
- assign a job to a crew on a specific date
- list crews
- landscaping job management
- equipment
- create invoice
- equipment fleet tracking
- payment processing
- customer account management
- list all crews and their members
- get details for a specific customer
- get customer
- list schedules
- list all crews
- list customer invoices with optional status filter
- process payment
- golf
- schedule a job for a crew
- list customers
- fleet management
- list jobs
- create a new customer
- list all customers
- invoicing
- smart connected products
- turf management
- scheduling
- list invoices
- create schedule entry
- list crew and job schedules for a date range
- process a payment
- list job schedules
- list landscaping jobs and work orders with optional status and date filters
- list payments
- list all landscape contractor customers
slug: landscape-operations
source_filename: landscape-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Toro Landscape Operations\n  description: Unified workflow capability for landscape contractors combining Horizon360 business management with IntelliDash\n    irrigation and fleet monitoring. Enables end-to-end operations from customer management and job scheduling through crew\n    dispatch, equipment tracking, and invoicing.\n  tags:\n  - Landscaping\n  - Business Management\n  - Operations\n  - Scheduling\n  - Invoicing\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HORIZON360_API_KEY: HORIZON360_API_KEY\n    INTELLIDASH_API_KEY: INTELLIDASH_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: horizon360\n    baseUri: https://api.horizon360.toro.com/v1\n    description: Toro Horizon360 business management API for landscape contractors\n    authentication:\n      type: bearer\n      token: '{{HORIZON360_API_KEY}}'\n    resources:\n    - name: customers\n      path: /customers\n\
  \      description: Customer account management\n      operations:\n      - name: list-customers\n        method: GET\n        description: List all customers for the account\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by name, email, or phone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create a new customer record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n    \
  \      type: json\n          data:\n            name: '{{tools.name}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n    - name: customer\n      path: /customers/{customerId}\n      description: Individual customer operations\n      operations:\n      - name: get-customer\n        method: GET\n        description: Retrieve a specific customer by ID\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      description: Landscaping job and work order management\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List jobs and work orders\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required:\
  \ false\n          description: Filter by job status\n        - name: customerId\n          in: query\n          type: string\n          required: false\n          description: Filter by customer\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Filter from date\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: Filter to date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job\n        method: POST\n        description: Create a new landscaping job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n            title: '{{tools.title}}'\n            jobType: '{{tools.jobType}}'\n\
  \            scheduledDate: '{{tools.scheduledDate}}'\n    - name: job\n      path: /jobs/{jobId}\n      description: Individual job operations\n      operations:\n      - name: get-job\n        method: GET\n        description: Retrieve a specific job by ID\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Job identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules\n      path: /schedules\n      description: Job and crew scheduling\n      operations:\n      - name: list-schedules\n        method: GET\n        description: List scheduled jobs for a date range\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start date\n        - name: endDate\n          in: query\n          type: string\n     \
  \     required: true\n          description: End date\n        - name: crewId\n          in: query\n          type: string\n          required: false\n          description: Filter by crew\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-schedule-entry\n        method: POST\n        description: Schedule a job for a crew\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            jobId: '{{tools.jobId}}'\n            crewId: '{{tools.crewId}}'\n            scheduledDate: '{{tools.scheduledDate}}'\n    - name: crews\n      path: /crews\n      description: Crew management\n      operations:\n      - name: list-crews\n        method: GET\n        description: List all crews and members\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: invoices\n      path: /invoices\n      description: Invoice management\n      operations:\n      - name: list-invoices\n        method: GET\n        description: List invoices\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by invoice status\n        - name: customerId\n          in: query\n          type: string\n          required: false\n          description: Filter by customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invoice\n        method: POST\n        description: Create a new invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n\
  \            jobId: '{{tools.jobId}}'\n            dueDate: '{{tools.dueDate}}'\n    - name: equipment\n      path: /equipment\n      description: Equipment fleet management\n      operations:\n      - name: list-equipment\n        method: GET\n        description: List fleet equipment\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by equipment status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments\n      path: /payments\n      description: Payment processing\n      operations:\n      - name: list-payments\n        method: GET\n        description: List payment transactions\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by payment status\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: process-payment\n        method: POST\n        description: Process a customer payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            invoiceId: '{{tools.invoiceId}}'\n            amount: '{{tools.amount}}'\n            paymentMethod: '{{tools.paymentMethod}}'\n  - type: http\n    namespace: intellidash\n    baseUri: https://api.intellidash.toro.com/v1\n    description: Toro IntelliDash irrigation and fleet management API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{INTELLIDASH_API_KEY}}'\n      placement: header\n    resources:\n    - name: irrigation-status\n      path: /irrigation/status\n      description: Irrigation system status\n      operations:\n      - name: get-irrigation-status\n        method: GET\n        description:\
  \ Get current status of all irrigation systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: irrigation-zones\n      path: /irrigation/zones\n      description: Irrigation zone management\n      operations:\n      - name: list-irrigation-zones\n        method: GET\n        description: List all irrigation zones\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by zone status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: irrigation-zone\n      path: /irrigation/zones/{zoneId}\n      description: Individual zone operations\n      operations:\n      - name: get-irrigation-zone\n        method: GET\n        description: Get a specific irrigation zone\n        inputParameters:\n        - name: zoneId\n  \
  \        in: path\n          type: string\n          required: true\n          description: Zone identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: start-zone-irrigation\n      path: /irrigation/zones/{zoneId}/start\n      description: Start irrigation for a zone\n      operations:\n      - name: start-irrigation\n        method: POST\n        description: Start manual irrigation for a zone\n        inputParameters:\n        - name: zoneId\n          in: path\n          type: string\n          required: true\n          description: Zone identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            duration: '{{tools.duration}}'\n    - name: stop-zone-irrigation\n      path: /irrigation/zones/{zoneId}/stop\n      description: Stop irrigation for a\
  \ zone\n      operations:\n      - name: stop-irrigation\n        method: POST\n        description: Stop active irrigation for a zone\n        inputParameters:\n        - name: zoneId\n          in: path\n          type: string\n          required: true\n          description: Zone identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment\n      path: /equipment\n      description: Fleet equipment tracking\n      operations:\n      - name: list-fleet-equipment\n        method: GET\n        description: List all fleet equipment with health data\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by equipment status\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by equipment type\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-item\n      path: /equipment/{equipmentId}\n      description: Individual equipment details\n      operations:\n      - name: get-fleet-equipment\n        method: GET\n        description: Get equipment health and details\n        inputParameters:\n        - name: equipmentId\n          in: path\n          type: string\n          required: true\n          description: Equipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-location\n      path: /equipment/{equipmentId}/location\n      description: Equipment GPS location\n      operations:\n      - name: get-equipment-location\n        method: GET\n        description: Get current GPS location of equipment\n        inputParameters:\n        - name: equipmentId\n          in: path\n          type: string\n \
  \         required: true\n          description: Equipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sensors\n      path: /sensors\n      description: Environmental and soil sensor monitoring\n      operations:\n      - name: list-sensors\n        method: GET\n        description: List all sensors and latest readings\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by sensor type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sensor-readings\n      path: /sensors/{sensorId}/readings\n      description: Historical sensor data\n      operations:\n      - name: get-sensor-readings\n        method: GET\n        description: Get historical sensor readings\n        inputParameters:\n        -\
  \ name: sensorId\n          in: path\n          type: string\n          required: true\n          description: Sensor identifier\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start of the time range\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: End of the time range\n        - name: interval\n          in: query\n          type: string\n          required: false\n          description: Data interval (15min, 1hour, 1day)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: water-usage-report\n      path: /reports/water-usage\n      description: Water usage reporting\n      operations:\n      - name: get-water-usage-report\n        method: GET\n        description: Get water usage summary report\n        inputParameters:\n        - name: startDate\n     \
  \     in: query\n          type: string\n          required: true\n          description: Start date\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: End date\n        - name: groupBy\n          in: query\n          type: string\n          required: false\n          description: Group results by day, week, month, or zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-health-report\n      path: /reports/equipment-health\n      description: Equipment health reporting\n      operations:\n      - name: get-equipment-health-report\n        method: GET\n        description: Get fleet equipment health summary\n        inputParameters:\n        - name: asOf\n          in: query\n          type: string\n          required: false\n          description: Report date\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: toro-landscape-api\n    description: Unified REST API for landscape business operations management.\n    resources:\n    - path: /v1/customers\n      name: customers\n      description: Customer account management\n      operations:\n      - method: GET\n        name: list-customers\n        description: List all customers\n        call: horizon360.list-customers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Create a new customer\n        call: horizon360.create-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{customerId}\n      name: customer\n      description: Individual customer management\n      operations:\n      - method: GET\n        name: get-customer\n        description: Get a customer\
  \ by ID\n        call: horizon360.get-customer\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Landscaping job management\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List landscaping jobs\n        call: horizon360.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-job\n        description: Create a new landscaping job\n        call: horizon360.create-job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/schedules\n      name: schedules\n      description: Crew and job scheduling\n      operations:\n      - method: GET\n        name: list-schedules\n        description: List job schedules\n        call: horizon360.list-schedules\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: create-schedule-entry\n        description: Schedule a job for a crew\n        call: horizon360.create-schedule-entry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/crews\n      name: crews\n      description: Crew management\n      operations:\n      - method: GET\n        name: list-crews\n        description: List all crews\n        call: horizon360.list-crews\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice management\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List invoices\n        call: horizon360.list-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-invoice\n        description: Create a new invoice\n        call: horizon360.create-invoice\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /v1/equipment\n      name: equipment\n      description: Equipment fleet tracking\n      operations:\n      - method: GET\n        name: list-equipment\n        description: List landscaping equipment\n        call: horizon360.list-equipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments\n      name: payments\n      description: Payment processing\n      operations:\n      - method: GET\n        name: list-payments\n        description: List payments\n        call: horizon360.list-payments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: process-payment\n        description: Process a payment\n        call: horizon360.process-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: toro-landscape-mcp\n    transport: http\n    description: MCP server\
  \ for AI-assisted landscape business operations management.\n    tools:\n    - name: list-customers\n      description: List all landscape contractor customers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: horizon360.list-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Create a new customer record for a landscape contractor\n      hints:\n        readOnly: false\n      call: horizon360.create-customer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Get details for a specific customer\n      hints:\n        readOnly: true\n        idempotent: true\n      call: horizon360.get-customer\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List landscaping jobs and work orders with optional status and date filters\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: horizon360.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-job\n      description: Create a new landscaping job for a customer\n      hints:\n        readOnly: false\n      call: horizon360.create-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-schedules\n      description: List crew and job schedules for a date range\n      hints:\n        readOnly: true\n        openWorld: true\n      call: horizon360.list-schedules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedule-job\n      description: Assign a job to a crew on a specific date\n      hints:\n        readOnly: false\n      call: horizon360.create-schedule-entry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-crews\n      description: List all crews and their members\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: horizon360.list-crews\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: List customer invoices with optional status filter\n      hints:\n        readOnly: true\n        openWorld: true\n      call: horizon360.list-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-invoice\n      description: Create a new invoice for a customer or completed job\n      hints:\n        readOnly: false\n      call: horizon360.create-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-equipment\n      description: List all landscaping equipment in the fleet\n      hints:\n        readOnly: true\n        openWorld: true\n      call: horizon360.list-equipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-payment\n      description: Process a customer payment for an invoice\n\
  \      hints:\n        readOnly: false\n        destructive: false\n      call: horizon360.process-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/toro/refs/heads/main/capabilities/landscape-operations.yaml
tags:
- Landscaping
- Business Management
- Operations
- Scheduling
- Invoicing
tools:
- description: List all landscape contractor customers
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Create a new customer record for a landscape contractor
  hints:
    readOnly: false
  name: create-customer
- description: Get details for a specific customer
  hints:
    idempotent: true
    readOnly: true
  name: get-customer
- description: List landscaping jobs and work orders with optional status and date filters
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Create a new landscaping job for a customer
  hints:
    readOnly: false
  name: create-job
- description: List crew and job schedules for a date range
  hints:
    openWorld: true
    readOnly: true
  name: list-schedules
- description: Assign a job to a crew on a specific date
  hints:
    readOnly: false
  name: schedule-job
- description: List all crews and their members
  hints:
    openWorld: true
    readOnly: true
  name: list-crews
- description: List customer invoices with optional status filter
  hints:
    openWorld: true
    readOnly: true
  name: list-invoices
- description: Create a new invoice for a customer or completed job
  hints:
    readOnly: false
  name: create-invoice
- description: List all landscaping equipment in the fleet
  hints:
    openWorld: true
    readOnly: true
  name: list-equipment
- description: Process a customer payment for an invoice
  hints:
    destructive: false
    readOnly: false
  name: process-payment
---
