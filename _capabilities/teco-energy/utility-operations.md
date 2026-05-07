---
categories: []
consumed_apis: []
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
- get account
- list service requests for a customer account.
- energy usage history for a customer account.
- service requests for a customer account.
- outage management
- get tampa electric customer account details including balance and service info.
- a specific tampa electric outage event.
- billing
- active power outages in the tampa electric service territory.
- natural gas
- list active tampa electric outages filtered by county or zip.
- get detailed status and restoration time for a tampa electric outage.
- smart grid
- list outages
- tampa electric customer account.
- create service request
- tampa electric
- get details for a specific tampa electric outage.
- list open and historical service requests for a tampa electric account.
- report a power outage at a tampa electric service address.
- utilities
- tampa bay
- teco energy
- get energy usage history with date range and interval filtering.
- get customer account details and current balance.
- get geographic outage map data for tampa electric service territory.
- list service requests
- list billing history for a tampa electric customer account.
- get historical energy consumption data for a tampa electric account.
- electric
- energy
- list bills
- submit a new service request.
- energy usage
- utility operations
- billing history for a customer account.
- list billing history for a customer account.
- customer service
- get outage
- get outage map
- submit a new service request (start service, stop service, meter read, etc.) for a tampa electric account.
- report outage
- list active tampa electric power outages. filter by county or zip code.
- get usage history
slug: utility-operations
source_filename: utility-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tampa Electric Utility Operations\n  description: Unified utility operations capability for Tampa Electric (TECO Energy), combining outage management and account\n    services into a single workflow. Enables customer service agents, field operations teams, and energy management applications\n    to manage power outages, monitor energy usage, handle billing, and process service requests across the Tampa Bay service\n    territory.\n  tags:\n  - TECO Energy\n  - Tampa Electric\n  - Utility Operations\n  - Outage Management\n  - Energy Usage\n  - Billing\n  - Customer Service\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TECO_API_TOKEN: TECO_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: teco-outage\n    baseUri: https://api.tecoenergy.com/v1\n    description: Tampa Electric Outage API for reporting and tracking power outages.\n    authentication:\n      type: bearer\n    \
  \  token: '{{TECO_API_TOKEN}}'\n    resources:\n    - name: outages\n      path: /outages\n      description: Active power outages in the Tampa Electric service territory.\n      operations:\n      - name: list-outages\n        method: GET\n        description: List active outages, filtered by county or ZIP code.\n        inputParameters:\n        - name: county\n          in: query\n          type: string\n          required: false\n          description: Filter outages by Florida county name.\n        - name: zipCode\n          in: query\n          type: string\n          required: false\n          description: Filter outages by ZIP code.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by outage status (active, restored, assessing).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-outage\n        method: GET\n\
  \        description: Get details for a specific outage event.\n        inputParameters:\n        - name: outageId\n          in: path\n          type: string\n          required: true\n          description: Unique outage event identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: report-outage\n        method: POST\n        description: Submit a power outage report for a service address.\n        body:\n          type: json\n          data:\n            accountNumber: '{{tools.accountNumber}}'\n            serviceAddress: '{{tools.serviceAddress}}'\n            hazardObserved: '{{tools.hazardObserved}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-outage-map\n        method: GET\n        description: Retrieve geographic outage map data.\n        inputParameters:\n        - name: bounds\n\
  \          in: query\n          type: string\n          required: false\n          description: Geographic bounding box.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: teco-account\n    baseUri: https://api.tecoenergy.com/v1\n    description: Tampa Electric Account API for customer account management.\n    authentication:\n      type: bearer\n      token: '{{TECO_API_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      description: Tampa Electric customer accounts.\n      operations:\n      - name: get-account\n        method: GET\n        description: Get customer account details.\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n          required: true\n          description: Customer account number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: usage\n      path: /accounts/{accountNumber}/usage\n      description: Energy usage history for a customer account.\n      operations:\n      - name: get-usage-history\n        method: GET\n        description: Get energy usage history by date range and interval.\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n          required: true\n          description: Customer account number.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date for usage history (YYYY-MM-DD).\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date for usage history (YYYY-MM-DD).\n        - name: interval\n          in: query\n          type: string\n          required: false\n          description: 'Data interval: hourly, daily, or monthly.'\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bills\n      path: /accounts/{accountNumber}/bills\n      description: Billing history for a customer account.\n      operations:\n      - name: list-bills\n        method: GET\n        description: List billing history for a customer account.\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n          required: true\n          description: Customer account number.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of bills to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-bill\n        method: GET\n        description: Get detailed information for a specific bill.\n        inputParameters:\n        - name: accountNumber\n          in:\
  \ path\n          type: string\n          required: true\n          description: Customer account number.\n        - name: billId\n          in: path\n          type: string\n          required: true\n          description: Unique bill identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: make-payment\n        method: POST\n        description: Submit a payment for a customer account.\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n          required: true\n          description: Customer account number.\n        body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n            paymentMethod: '{{tools.paymentMethod}}'\n            paymentDate: '{{tools.paymentDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ service-requests\n      path: /accounts/{accountNumber}/service-requests\n      description: Service requests for a customer account.\n      operations:\n      - name: list-service-requests\n        method: GET\n        description: List service requests for a customer account.\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n          required: true\n          description: Customer account number.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by service request status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-service-request\n        method: POST\n        description: Submit a new service request.\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n          required: true\n          description:\
  \ Customer account number.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            preferredDate: '{{tools.preferredDate}}'\n            notes: '{{tools.notes}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: teco-utility-api\n    description: Unified REST API for Tampa Electric utility operations.\n    resources:\n    - path: /v1/outages\n      name: outages\n      description: Active power outages in the Tampa Electric service territory.\n      operations:\n      - method: GET\n        name: list-outages\n        description: List active Tampa Electric outages filtered by county or ZIP.\n        call: teco-outage.list-outages\n        with:\n          county: rest.county\n          zipCode: rest.zipCode\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/outages/{outageId}\n      name: outage\n      description: A specific Tampa Electric outage event.\n      operations:\n      - method: GET\n        name: get-outage\n        description: Get details for a specific Tampa Electric outage.\n        call: teco-outage.get-outage\n        with:\n          outageId: rest.outageId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountNumber}\n      name: account\n      description: Tampa Electric customer account.\n      operations:\n      - method: GET\n        name: get-account\n        description: Get customer account details and current balance.\n        call: teco-account.get-account\n        with:\n          accountNumber: rest.accountNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountNumber}/usage\n      name: usage\n      description: Energy usage history for a customer account.\n      operations:\n\
  \      - method: GET\n        name: get-usage-history\n        description: Get energy usage history with date range and interval filtering.\n        call: teco-account.get-usage-history\n        with:\n          accountNumber: rest.accountNumber\n          startDate: rest.startDate\n          endDate: rest.endDate\n          interval: rest.interval\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountNumber}/bills\n      name: bills\n      description: Billing history for a customer account.\n      operations:\n      - method: GET\n        name: list-bills\n        description: List billing history for a customer account.\n        call: teco-account.list-bills\n        with:\n          accountNumber: rest.accountNumber\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/accounts/{accountNumber}/service-requests\n      name: service-requests\n      description: Service\
  \ requests for a customer account.\n      operations:\n      - method: GET\n        name: list-service-requests\n        description: List service requests for a customer account.\n        call: teco-account.list-service-requests\n        with:\n          accountNumber: rest.accountNumber\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-service-request\n        description: Submit a new service request.\n        call: teco-account.create-service-request\n        with:\n          accountNumber: rest.accountNumber\n          type: rest.type\n          preferredDate: rest.preferredDate\n          notes: rest.notes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: teco-utility-mcp\n    transport: http\n    description: MCP server for AI-assisted Tampa Electric utility operations.\n    tools:\n    - name: list-outages\n      description: List active Tampa\
  \ Electric power outages. Filter by county or ZIP code.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: teco-outage.list-outages\n      with:\n        county: tools.county\n        zipCode: tools.zipCode\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-outage\n      description: Get detailed status and restoration time for a Tampa Electric outage.\n      hints:\n        readOnly: true\n      call: teco-outage.get-outage\n      with:\n        outageId: tools.outageId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: report-outage\n      description: Report a power outage at a Tampa Electric service address.\n      hints:\n        readOnly: false\n        destructive: false\n      call: teco-outage.report-outage\n      with:\n        accountNumber: tools.accountNumber\n        serviceAddress: tools.serviceAddress\n        hazardObserved: tools.hazardObserved\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-outage-map\n      description: Get geographic outage map data for Tampa Electric service territory.\n      hints:\n        readOnly: true\n      call: teco-outage.get-outage-map\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Get Tampa Electric customer account details including balance and service info.\n      hints:\n        readOnly: true\n      call: teco-account.get-account\n      with:\n        accountNumber: tools.accountNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-usage-history\n      description: Get historical energy consumption data for a Tampa Electric account.\n      hints:\n        readOnly: true\n      call: teco-account.get-usage-history\n      with:\n        accountNumber: tools.accountNumber\n        startDate: tools.startDate\n        endDate: tools.endDate\n        interval: tools.interval\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bills\n      description: List billing history for a Tampa Electric customer account.\n      hints:\n        readOnly: true\n      call: teco-account.list-bills\n      with:\n        accountNumber: tools.accountNumber\n        limit: tools.limit\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-service-requests\n      description: List open and historical service requests for a Tampa Electric account.\n      hints:\n        readOnly: true\n      call: teco-account.list-service-requests\n      with:\n        accountNumber: tools.accountNumber\n        status: tools.status\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-service-request\n      description: Submit a new service request (start service, stop service, meter read, etc.) for a Tampa Electric account.\n      hints:\n        readOnly: false\n        destructive: false\n  \
  \    call: teco-account.create-service-request\n      with:\n        accountNumber: tools.accountNumber\n        type: tools.type\n        preferredDate: tools.preferredDate\n        notes: tools.notes\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
