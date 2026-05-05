---
categories: []
consumed_apis:
- teco-outage
- teco-account
description: Unified utility operations capability for Tampa Electric (TECO Energy), combining outage management and account services into a single workflow. Enables customer service agents, field operations teams, and energy management applications to manage power outages, monitor energy usage, handle billing, and process service requests across the Tampa Bay service territory.
layout: capability
name: Tampa Electric Utility Operations
operations:
- description: List active Tampa Electric outages filtered by county or ZIP.
  method: GET
  name: list-outages
  path: /v1/outages
- description: Get details for a specific Tampa Electric outage.
  method: GET
  name: get-outage
  path: /v1/outages/{outageId}
- description: Get customer account details and current balance.
  method: GET
  name: get-account
  path: /v1/accounts/{accountNumber}
- description: Get energy usage history with date range and interval filtering.
  method: GET
  name: get-usage-history
  path: /v1/accounts/{accountNumber}/usage
- description: List billing history for a customer account.
  method: GET
  name: list-bills
  path: /v1/accounts/{accountNumber}/bills
- description: List service requests for a customer account.
  method: GET
  name: list-service-requests
  path: /v1/accounts/{accountNumber}/service-requests
- description: Submit a new service request.
  method: POST
  name: create-service-request
  path: /v1/accounts/{accountNumber}/service-requests
personas: []
provider_name: TECO Energy
provider_slug: teco-energy
search_terms:
- get geographic outage map data for tampa electric service territory.
- tampa electric customer account.
- list active tampa electric outages filtered by county or zip.
- list billing history for a tampa electric customer account.
- active power outages in the tampa electric service territory.
- get usage history
- get historical energy consumption data for a tampa electric account.
- list bills
- get account
- billing
- list service requests
- get detailed status and restoration time for a tampa electric outage.
- get energy usage history with date range and interval filtering.
- teco energy
- get outage map
- tampa bay
- billing history for a customer account.
- outage management
- utility operations
- create service request
- natural gas
- submit a new service request.
- get outage
- get tampa electric customer account details including balance and service info.
- list service requests for a customer account.
- list outages
- energy usage history for a customer account.
- submit a new service request (start service, stop service, meter read, etc.) for a tampa electric account.
- list billing history for a customer account.
- a specific tampa electric outage event.
- smart grid
- report a power outage at a tampa electric service address.
- energy usage
- utilities
- get customer account details and current balance.
- energy
- service requests for a customer account.
- list open and historical service requests for a tampa electric account.
- get details for a specific tampa electric outage.
- list active tampa electric power outages. filter by county or zip code.
- tampa electric
- report outage
- electric
- customer service
slug: utility-operations
source_filename: utility-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tampa Electric Utility Operations\"\n  description: >-\n    Unified utility operations capability for Tampa Electric (TECO Energy),\n    combining outage management and account services into a single workflow.\n    Enables customer service agents, field operations teams, and energy management\n    applications to manage power outages, monitor energy usage, handle billing,\n    and process service requests across the Tampa Bay service territory.\n  tags:\n    - TECO Energy\n    - Tampa Electric\n    - Utility Operations\n    - Outage Management\n    - Energy Usage\n    - Billing\n    - Customer Service\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TECO_API_TOKEN: TECO_API_TOKEN\n\ncapability:\n  consumes:\n    - import: teco-outage\n      location: ./shared/outage-api.yaml\n    - import: teco-account\n      location: ./shared/account-api.yaml\n\n  exposes:\n    - type: rest\n\
  \      port: 8080\n      namespace: teco-utility-api\n      description: \"Unified REST API for Tampa Electric utility operations.\"\n      resources:\n        - path: /v1/outages\n          name: outages\n          description: \"Active power outages in the Tampa Electric service territory.\"\n          operations:\n            - method: GET\n              name: list-outages\n              description: \"List active Tampa Electric outages filtered by county or ZIP.\"\n              call: \"teco-outage.list-outages\"\n              with:\n                county: \"rest.county\"\n                zipCode: \"rest.zipCode\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/outages/{outageId}\n          name: outage\n          description: \"A specific Tampa Electric outage event.\"\n          operations:\n            - method: GET\n              name: get-outage\n             \
  \ description: \"Get details for a specific Tampa Electric outage.\"\n              call: \"teco-outage.get-outage\"\n              with:\n                outageId: \"rest.outageId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountNumber}\n          name: account\n          description: \"Tampa Electric customer account.\"\n          operations:\n            - method: GET\n              name: get-account\n              description: \"Get customer account details and current balance.\"\n              call: \"teco-account.get-account\"\n              with:\n                accountNumber: \"rest.accountNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountNumber}/usage\n          name: usage\n          description: \"Energy usage history for a customer account.\"\n          operations:\n            - method:\
  \ GET\n              name: get-usage-history\n              description: \"Get energy usage history with date range and interval filtering.\"\n              call: \"teco-account.get-usage-history\"\n              with:\n                accountNumber: \"rest.accountNumber\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                interval: \"rest.interval\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountNumber}/bills\n          name: bills\n          description: \"Billing history for a customer account.\"\n          operations:\n            - method: GET\n              name: list-bills\n              description: \"List billing history for a customer account.\"\n              call: \"teco-account.list-bills\"\n              with:\n                accountNumber: \"rest.accountNumber\"\n                limit: \"rest.limit\"\n              outputParameters:\n\
  \                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountNumber}/service-requests\n          name: service-requests\n          description: \"Service requests for a customer account.\"\n          operations:\n            - method: GET\n              name: list-service-requests\n              description: \"List service requests for a customer account.\"\n              call: \"teco-account.list-service-requests\"\n              with:\n                accountNumber: \"rest.accountNumber\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-service-request\n              description: \"Submit a new service request.\"\n              call: \"teco-account.create-service-request\"\n              with:\n                accountNumber: \"rest.accountNumber\"\n                type: \"rest.type\"\n                preferredDate: \"rest.preferredDate\"\
  \n                notes: \"rest.notes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: teco-utility-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Tampa Electric utility operations.\"\n      tools:\n        - name: list-outages\n          description: \"List active Tampa Electric power outages. Filter by county or ZIP code.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"teco-outage.list-outages\"\n          with:\n            county: \"tools.county\"\n            zipCode: \"tools.zipCode\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-outage\n          description: \"Get detailed status and restoration time for a Tampa Electric outage.\"\n          hints:\n            readOnly: true\n          call: \"\
  teco-outage.get-outage\"\n          with:\n            outageId: \"tools.outageId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: report-outage\n          description: \"Report a power outage at a Tampa Electric service address.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"teco-outage.report-outage\"\n          with:\n            accountNumber: \"tools.accountNumber\"\n            serviceAddress: \"tools.serviceAddress\"\n            hazardObserved: \"tools.hazardObserved\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-outage-map\n          description: \"Get geographic outage map data for Tampa Electric service territory.\"\n          hints:\n            readOnly: true\n          call: \"teco-outage.get-outage-map\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n\
  \        - name: get-account\n          description: \"Get Tampa Electric customer account details including balance and service info.\"\n          hints:\n            readOnly: true\n          call: \"teco-account.get-account\"\n          with:\n            accountNumber: \"tools.accountNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-usage-history\n          description: \"Get historical energy consumption data for a Tampa Electric account.\"\n          hints:\n            readOnly: true\n          call: \"teco-account.get-usage-history\"\n          with:\n            accountNumber: \"tools.accountNumber\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            interval: \"tools.interval\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-bills\n          description: \"List billing history for a Tampa Electric customer\
  \ account.\"\n          hints:\n            readOnly: true\n          call: \"teco-account.list-bills\"\n          with:\n            accountNumber: \"tools.accountNumber\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-service-requests\n          description: \"List open and historical service requests for a Tampa Electric account.\"\n          hints:\n            readOnly: true\n          call: \"teco-account.list-service-requests\"\n          with:\n            accountNumber: \"tools.accountNumber\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-service-request\n          description: \"Submit a new service request (start service, stop service, meter read, etc.) for a Tampa Electric account.\"\n          hints:\n            readOnly: false\n            destructive: false\n         \
  \ call: \"teco-account.create-service-request\"\n          with:\n            accountNumber: \"tools.accountNumber\"\n            type: \"tools.type\"\n            preferredDate: \"tools.preferredDate\"\n            notes: \"tools.notes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/teco-energy/refs/heads/main/capabilities/utility-operations.yaml
tags:
- TECO Energy
- Tampa Electric
- Utility Operations
- Outage Management
- Energy Usage
- Billing
- Customer Service
tools:
- description: List active Tampa Electric power outages. Filter by county or ZIP code.
  hints:
    openWorld: true
    readOnly: true
  name: list-outages
- description: Get detailed status and restoration time for a Tampa Electric outage.
  hints:
    readOnly: true
  name: get-outage
- description: Report a power outage at a Tampa Electric service address.
  hints:
    destructive: false
    readOnly: false
  name: report-outage
- description: Get geographic outage map data for Tampa Electric service territory.
  hints:
    readOnly: true
  name: get-outage-map
- description: Get Tampa Electric customer account details including balance and service info.
  hints:
    readOnly: true
  name: get-account
- description: Get historical energy consumption data for a Tampa Electric account.
  hints:
    readOnly: true
  name: get-usage-history
- description: List billing history for a Tampa Electric customer account.
  hints:
    readOnly: true
  name: list-bills
- description: List open and historical service requests for a Tampa Electric account.
  hints:
    readOnly: true
  name: list-service-requests
- description: Submit a new service request (start service, stop service, meter read, etc.) for a Tampa Electric account.
  hints:
    destructive: false
    readOnly: false
  name: create-service-request
---
