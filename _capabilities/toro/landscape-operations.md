---
categories: []
consumed_apis:
- horizon360
- intellidash
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
- smart connected products
- create a new customer record for a landscape contractor
- list payments
- process a customer payment for an invoice
- list equipment
- create a new landscaping job for a customer
- list crew and job schedules for a date range
- customer account management
- list all crews and their members
- schedule a job for a crew
- list landscaping equipment
- landscaping job management
- golf
- process a payment
- equipment
- operations
- individual customer management
- crew management
- process payment
- create a new invoice
- list customer invoices with optional status filter
- list all crews
- create a new landscaping job
- list all landscaping equipment in the fleet
- invoice management
- list jobs
- get details for a specific customer
- list landscaping jobs and work orders with optional status and date filters
- landscaping
- list invoices
- list crews
- irrigation
- business management
- list all landscape contractor customers
- schedule job
- create a new invoice for a customer or completed job
- list customers
- create a new customer
- scheduling
- create schedule entry
- list job schedules
- assign a job to a crew on a specific date
- get customer
- list landscaping jobs
- crew and job scheduling
- create customer
- fleet management
- equipment fleet tracking
- list all customers
- turf management
- list schedules
- create invoice
- invoicing
- payment processing
- create job
- get a customer by id
slug: landscape-operations
source_filename: landscape-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Toro Landscape Operations\"\n  description: \"Unified workflow capability for landscape contractors combining Horizon360 business management with IntelliDash irrigation and fleet monitoring. Enables end-to-end operations from customer management and job scheduling through crew dispatch, equipment tracking, and invoicing.\"\n  tags:\n    - Landscaping\n    - Business Management\n    - Operations\n    - Scheduling\n    - Invoicing\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      HORIZON360_API_KEY: HORIZON360_API_KEY\n      INTELLIDASH_API_KEY: INTELLIDASH_API_KEY\n\ncapability:\n  consumes:\n    - import: horizon360\n      location: ./shared/horizon360.yaml\n    - import: intellidash\n      location: ./shared/intellidash.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: toro-landscape-api\n      description: \"Unified REST API for landscape business operations\
  \ management.\"\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: \"Customer account management\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List all customers\"\n              call: \"horizon360.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Create a new customer\"\n              call: \"horizon360.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{customerId}\n          name: customer\n          description: \"Individual customer management\"\n          operations:\n            - method: GET\n              name: get-customer\n              description: \"Get a customer by ID\"\n              call: \"horizon360.get-customer\"\
  \n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: \"Landscaping job management\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List landscaping jobs\"\n              call: \"horizon360.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-job\n              description: \"Create a new landscaping job\"\n              call: \"horizon360.create-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/schedules\n          name: schedules\n          description: \"Crew and job scheduling\"\n          operations:\n            - method: GET\n              name:\
  \ list-schedules\n              description: \"List job schedules\"\n              call: \"horizon360.list-schedules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-schedule-entry\n              description: \"Schedule a job for a crew\"\n              call: \"horizon360.create-schedule-entry\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/crews\n          name: crews\n          description: \"Crew management\"\n          operations:\n            - method: GET\n              name: list-crews\n              description: \"List all crews\"\n              call: \"horizon360.list-crews\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices\n          name: invoices\n          description: \"Invoice management\"\n          operations:\n\
  \            - method: GET\n              name: list-invoices\n              description: \"List invoices\"\n              call: \"horizon360.list-invoices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-invoice\n              description: \"Create a new invoice\"\n              call: \"horizon360.create-invoice\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/equipment\n          name: equipment\n          description: \"Equipment fleet tracking\"\n          operations:\n            - method: GET\n              name: list-equipment\n              description: \"List landscaping equipment\"\n              call: \"horizon360.list-equipment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments\n          name: payments\n         \
  \ description: \"Payment processing\"\n          operations:\n            - method: GET\n              name: list-payments\n              description: \"List payments\"\n              call: \"horizon360.list-payments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: process-payment\n              description: \"Process a payment\"\n              call: \"horizon360.process-payment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: toro-landscape-mcp\n      transport: http\n      description: \"MCP server for AI-assisted landscape business operations management.\"\n      tools:\n        - name: list-customers\n          description: \"List all landscape contractor customers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"horizon360.list-customers\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: \"Create a new customer record for a landscape contractor\"\n          hints:\n            readOnly: false\n          call: \"horizon360.create-customer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer\n          description: \"Get details for a specific customer\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"horizon360.get-customer\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jobs\n          description: \"List landscaping jobs and work orders with optional status and date filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"horizon360.list-jobs\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-job\n          description: \"Create a new landscaping job for a customer\"\n          hints:\n            readOnly: false\n          call: \"horizon360.create-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-schedules\n          description: \"List crew and job schedules for a date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"horizon360.list-schedules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: schedule-job\n          description: \"Assign a job to a crew on a specific date\"\n          hints:\n            readOnly: false\n          call: \"horizon360.create-schedule-entry\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-crews\n\
  \          description: \"List all crews and their members\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"horizon360.list-crews\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-invoices\n          description: \"List customer invoices with optional status filter\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"horizon360.list-invoices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-invoice\n          description: \"Create a new invoice for a customer or completed job\"\n          hints:\n            readOnly: false\n          call: \"horizon360.create-invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-equipment\n          description: \"List all landscaping equipment in the fleet\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"horizon360.list-equipment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: process-payment\n          description: \"Process a customer payment for an invoice\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"horizon360.process-payment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
