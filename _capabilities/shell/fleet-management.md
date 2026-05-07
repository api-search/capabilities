---
categories: []
consumed_apis: []
description: Unified fleet management workflow combining B2B mobility card management, transaction reporting, invoice management, and site location data. Designed for fleet managers and corporate finance teams managing fuel cards across the Shell global network.
layout: capability
name: Shell Fleet Management
operations:
- description: List all fuel cards for the fleet
  method: GET
  name: list-cards
  path: /v1/cards
- description: Order a new fuel card for a driver or vehicle
  method: POST
  name: order-card
  path: /v1/cards
- description: Block or unblock a card
  method: POST
  name: block-card
  path: /v1/cards/{id}/block
- description: Retrieve fleet transaction history
  method: GET
  name: list-transactions
  path: /v1/transactions
- description: List fuel invoices for the fleet account
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Find Shell sites near a location
  method: GET
  name: list-sites
  path: /v1/sites
- description: Update spending limits for a fuel card
  method: POST
  name: update-limits
  path: /v1/card-limits
personas: []
provider_name: Shell
provider_slug: shell
search_terms:
- block or unblock a card
- mobility
- transactions
- update spending limits for a fuel card
- list all fuel cards for the fleet with status and driver information
- list cards
- list fuel card transactions for date range with spend analytics
- find shell stations
- block or unblock a fuel card for a driver or vehicle
- order a new shell fuel card for a driver or vehicle
- loyalty
- update limits
- retrieve fleet transaction history
- find shell sites near a location
- b2b
- list fuel invoices for the fleet account
- shell fuel and ev charging site locations
- update spending limits and restrictions on a fuel card
- manage fleet fuel cards
- electric vehicle charging
- list sites
- list fleet invoices
- list all fuel cards for the fleet
- list fleet transactions
- lubricants
- find shell fuel and ev charging stations near a location
- block or unblock a fuel card
- block fuel card
- energy
- aviation
- renewable energy
- fleet fuel transaction data
- fleet management
- order card
- order a new fuel card for a driver or vehicle
- update card spending limits
- oil and gas
- gas
- block card
- list invoices
- manage card spending limits
- fuel
- list transactions
- list fleet cards
- order fuel card
- fleet fuel invoices
slug: fleet-management
source_filename: fleet-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Shell Fleet Management\n  description: Unified fleet management workflow combining B2B mobility card management, transaction reporting, invoice management,\n    and site location data. Designed for fleet managers and corporate finance teams managing fuel cards across the Shell global\n    network.\n  tags:\n  - B2B\n  - Energy\n  - Fleet Management\n  - Fuel\n  - Mobility\n  - Transactions\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHELL_MOBILITY_TOKEN: SHELL_MOBILITY_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: shell-mobility\n    baseUri: https://api.shell.com/mobility/v2\n    description: Shell B2B Mobility fleet management API\n    authentication:\n      type: bearer\n      token: '{{SHELL_MOBILITY_TOKEN}}'\n    resources:\n    - name: cards\n      path: /cards\n      description: Manage B2B fuel cards\n      operations:\n      - name: list-cards\n        method: GET\n\
  \        description: List fuel cards for a B2B account\n        inputParameters:\n        - name: colCoCode\n          in: query\n          type: integer\n          required: true\n          description: Collecting Company country code\n        - name: payerNumber\n          in: query\n          type: string\n          required: false\n          description: Payer account number\n        - name: cardStatus\n          in: query\n          type: string\n          required: false\n          description: Filter by card status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: order-card\n        method: POST\n        description: Order a new fuel card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            colCoCode: '{{tools.col_co_code}}'\n            accountNumber:\
  \ '{{tools.account_number}}'\n            driverName: '{{tools.driver_name}}'\n            vehicleRegistration: '{{tools.vehicle_registration}}'\n      - name: block-card\n        method: POST\n        description: Block or unblock a fuel card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            colCoCode: '{{tools.col_co_code}}'\n            action: '{{tools.action}}'\n    - name: transactions\n      path: /transactions\n      description: Retrieve fuel card transaction data\n      operations:\n      - name: list-transactions\n        method: GET\n        description: List fuel card transactions for a date range\n        inputParameters:\n        - name: colCoCode\n          in: query\n          type: integer\n          required: true\n          description: Collecting Company country code\n        - name: payerNumber\n          in: query\n     \
  \     type: string\n          required: false\n          description: Payer account number\n        - name: fromDate\n          in: query\n          type: string\n          required: true\n          description: Start date (YYYY-MM-DD)\n        - name: toDate\n          in: query\n          type: string\n          required: true\n          description: End date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /invoices\n      description: Access fuel card invoices\n      operations:\n      - name: list-invoices\n        method: GET\n        description: List invoices for a B2B account\n        inputParameters:\n        - name: colCoCode\n          in: query\n          type: integer\n          required: true\n          description: Collecting Company country code\n        - name: payerNumber\n          in: query\n          type: string\n          required: false\n\
  \          description: Payer account number\n        - name: invoiceDateFrom\n          in: query\n          type: string\n          required: false\n          description: Invoice date from\n        - name: invoiceDateTo\n          in: query\n          type: string\n          required: false\n          description: Invoice date to\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites\n      path: /sites\n      description: Query Shell fuel and EV charging sites\n      operations:\n      - name: list-sites\n        method: GET\n        description: List Shell sites by location or country\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: false\n          description: Latitude for location search\n        - name: longitude\n          in: query\n          type: number\n          required: false\n          description: Longitude for\
  \ location search\n        - name: radius\n          in: query\n          type: number\n          required: false\n          description: Search radius in kilometers\n        - name: countryCode\n          in: query\n          type: string\n          required: false\n          description: ISO country code\n        - name: evCharging\n          in: query\n          type: boolean\n          required: false\n          description: Filter for EV charging sites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: limits\n      path: /limits\n      description: Manage card spending limits\n      operations:\n      - name: update-card-limits\n        method: POST\n        description: Update spending limits for a fuel card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n   \
  \         colCoCode: '{{tools.col_co_code}}'\n            cardId: '{{tools.card_id}}'\n            limits: '{{tools.limits}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: shell-fleet-api\n    description: Unified REST API for Shell B2B fleet fuel card management and reporting.\n    resources:\n    - path: /v1/cards\n      name: cards\n      description: Manage fleet fuel cards\n      operations:\n      - method: GET\n        name: list-cards\n        description: List all fuel cards for the fleet\n        call: shell-mobility.list-cards\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: order-card\n        description: Order a new fuel card for a driver or vehicle\n        call: shell-mobility.order-card\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cards/{id}/block\n      name: card-block\n      description: Block or unblock a fuel card\n      operations:\n      - method:\
  \ POST\n        name: block-card\n        description: Block or unblock a card\n        call: shell-mobility.block-card\n        with:\n          card_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions\n      name: transactions\n      description: Fleet fuel transaction data\n      operations:\n      - method: GET\n        name: list-transactions\n        description: Retrieve fleet transaction history\n        call: shell-mobility.list-transactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Fleet fuel invoices\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List fuel invoices for the fleet account\n        call: shell-mobility.list-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sites\n      name: sites\n      description: Shell fuel\
  \ and EV charging site locations\n      operations:\n      - method: GET\n        name: list-sites\n        description: Find Shell sites near a location\n        call: shell-mobility.list-sites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/card-limits\n      name: card-limits\n      description: Manage card spending limits\n      operations:\n      - method: POST\n        name: update-limits\n        description: Update spending limits for a fuel card\n        call: shell-mobility.update-card-limits\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: shell-fleet-mcp\n    transport: http\n    description: MCP server for AI-assisted fleet fuel card management and reporting.\n    tools:\n    - name: list-fleet-cards\n      description: List all fuel cards for the fleet with status and driver information\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ shell-mobility.list-cards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: order-fuel-card\n      description: Order a new Shell fuel card for a driver or vehicle\n      hints:\n        readOnly: false\n      call: shell-mobility.order-card\n      with:\n        col_co_code: tools.col_co_code\n        account_number: tools.account_number\n        driver_name: tools.driver_name\n        vehicle_registration: tools.vehicle_registration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: block-fuel-card\n      description: Block or unblock a fuel card for a driver or vehicle\n      hints:\n        readOnly: false\n        destructive: false\n      call: shell-mobility.block-card\n      with:\n        col_co_code: tools.col_co_code\n        action: tools.action\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-fleet-transactions\n      description: List fuel card transactions for date range with\
  \ spend analytics\n      hints:\n        readOnly: true\n      call: shell-mobility.list-transactions\n      with:\n        colCoCode: tools.col_co_code\n        fromDate: tools.from_date\n        toDate: tools.to_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-fleet-invoices\n      description: List fuel invoices for the fleet account\n      hints:\n        readOnly: true\n      call: shell-mobility.list-invoices\n      with:\n        colCoCode: tools.col_co_code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-shell-stations\n      description: Find Shell fuel and EV charging stations near a location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shell-mobility.list-sites\n      with:\n        latitude: tools.latitude\n        longitude: tools.longitude\n        radius: tools.radius\n        evCharging: tools.ev_charging\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: update-card-spending-limits\n      description: Update spending limits and restrictions on a fuel card\n      hints:\n        readOnly: false\n      call: shell-mobility.update-card-limits\n      with:\n        col_co_code: tools.col_co_code\n        card_id: tools.card_id\n        limits: tools.limits\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shell/refs/heads/main/capabilities/fleet-management.yaml
tags:
- B2B
- Energy
- Fleet Management
- Fuel
- Mobility
- Transactions
tools:
- description: List all fuel cards for the fleet with status and driver information
  hints:
    openWorld: true
    readOnly: true
  name: list-fleet-cards
- description: Order a new Shell fuel card for a driver or vehicle
  hints:
    readOnly: false
  name: order-fuel-card
- description: Block or unblock a fuel card for a driver or vehicle
  hints:
    destructive: false
    readOnly: false
  name: block-fuel-card
- description: List fuel card transactions for date range with spend analytics
  hints:
    readOnly: true
  name: list-fleet-transactions
- description: List fuel invoices for the fleet account
  hints:
    readOnly: true
  name: list-fleet-invoices
- description: Find Shell fuel and EV charging stations near a location
  hints:
    openWorld: true
    readOnly: true
  name: find-shell-stations
- description: Update spending limits and restrictions on a fuel card
  hints:
    readOnly: false
  name: update-card-spending-limits
---
