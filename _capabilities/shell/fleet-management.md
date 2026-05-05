---
categories: []
consumed_apis:
- shell-mobility
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
- manage fleet fuel cards
- update spending limits and restrictions on a fuel card
- renewable energy
- list sites
- list fuel invoices for the fleet account
- list all fuel cards for the fleet
- order a new shell fuel card for a driver or vehicle
- retrieve fleet transaction history
- fleet fuel invoices
- order fuel card
- order a new fuel card for a driver or vehicle
- list cards
- update spending limits for a fuel card
- update limits
- mobility
- block or unblock a card
- list fuel card transactions for date range with spend analytics
- block or unblock a fuel card
- list fleet transactions
- list invoices
- find shell fuel and ev charging stations near a location
- gas
- block card
- electric vehicle charging
- loyalty
- fleet fuel transaction data
- oil and gas
- fuel
- shell fuel and ev charging site locations
- b2b
- list transactions
- list all fuel cards for the fleet with status and driver information
- list fleet invoices
- find shell sites near a location
- block or unblock a fuel card for a driver or vehicle
- manage card spending limits
- find shell stations
- update card spending limits
- lubricants
- energy
- order card
- list fleet cards
- transactions
- block fuel card
- aviation
- fleet management
slug: fleet-management
source_filename: fleet-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Shell Fleet Management\"\n  description: >-\n    Unified fleet management workflow combining B2B mobility card management,\n    transaction reporting, invoice management, and site location data. Designed\n    for fleet managers and corporate finance teams managing fuel cards across\n    the Shell global network.\n  tags:\n    - B2B\n    - Energy\n    - Fleet Management\n    - Fuel\n    - Mobility\n    - Transactions\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SHELL_MOBILITY_TOKEN: SHELL_MOBILITY_TOKEN\n\ncapability:\n  consumes:\n    - import: shell-mobility\n      location: ./shared/b2b-mobility.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: shell-fleet-api\n      description: \"Unified REST API for Shell B2B fleet fuel card management and reporting.\"\n      resources:\n        - path: /v1/cards\n          name: cards\n          description:\
  \ \"Manage fleet fuel cards\"\n          operations:\n            - method: GET\n              name: list-cards\n              description: \"List all fuel cards for the fleet\"\n              call: \"shell-mobility.list-cards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: order-card\n              description: \"Order a new fuel card for a driver or vehicle\"\n              call: \"shell-mobility.order-card\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cards/{id}/block\n          name: card-block\n          description: \"Block or unblock a fuel card\"\n          operations:\n            - method: POST\n              name: block-card\n              description: \"Block or unblock a card\"\n              call: \"shell-mobility.block-card\"\n              with:\n                card_id: \"rest.id\"\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transactions\n          name: transactions\n          description: \"Fleet fuel transaction data\"\n          operations:\n            - method: GET\n              name: list-transactions\n              description: \"Retrieve fleet transaction history\"\n              call: \"shell-mobility.list-transactions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices\n          name: invoices\n          description: \"Fleet fuel invoices\"\n          operations:\n            - method: GET\n              name: list-invoices\n              description: \"List fuel invoices for the fleet account\"\n              call: \"shell-mobility.list-invoices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sites\n          name: sites\n      \
  \    description: \"Shell fuel and EV charging site locations\"\n          operations:\n            - method: GET\n              name: list-sites\n              description: \"Find Shell sites near a location\"\n              call: \"shell-mobility.list-sites\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/card-limits\n          name: card-limits\n          description: \"Manage card spending limits\"\n          operations:\n            - method: POST\n              name: update-limits\n              description: \"Update spending limits for a fuel card\"\n              call: \"shell-mobility.update-card-limits\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: shell-fleet-mcp\n      transport: http\n      description: \"MCP server for AI-assisted fleet fuel card management and reporting.\"\n      tools:\n \
  \       - name: list-fleet-cards\n          description: \"List all fuel cards for the fleet with status and driver information\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shell-mobility.list-cards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: order-fuel-card\n          description: \"Order a new Shell fuel card for a driver or vehicle\"\n          hints:\n            readOnly: false\n          call: \"shell-mobility.order-card\"\n          with:\n            col_co_code: \"tools.col_co_code\"\n            account_number: \"tools.account_number\"\n            driver_name: \"tools.driver_name\"\n            vehicle_registration: \"tools.vehicle_registration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: block-fuel-card\n          description: \"Block or unblock a fuel card for a driver or vehicle\"\n          hints:\n\
  \            readOnly: false\n            destructive: false\n          call: \"shell-mobility.block-card\"\n          with:\n            col_co_code: \"tools.col_co_code\"\n            action: \"tools.action\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-fleet-transactions\n          description: \"List fuel card transactions for date range with spend analytics\"\n          hints:\n            readOnly: true\n          call: \"shell-mobility.list-transactions\"\n          with:\n            colCoCode: \"tools.col_co_code\"\n            fromDate: \"tools.from_date\"\n            toDate: \"tools.to_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-fleet-invoices\n          description: \"List fuel invoices for the fleet account\"\n          hints:\n            readOnly: true\n          call: \"shell-mobility.list-invoices\"\n          with:\n            colCoCode:\
  \ \"tools.col_co_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-shell-stations\n          description: \"Find Shell fuel and EV charging stations near a location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shell-mobility.list-sites\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            radius: \"tools.radius\"\n            evCharging: \"tools.ev_charging\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-card-spending-limits\n          description: \"Update spending limits and restrictions on a fuel card\"\n          hints:\n            readOnly: false\n          call: \"shell-mobility.update-card-limits\"\n          with:\n            col_co_code: \"tools.col_co_code\"\n            card_id: \"tools.card_id\"\n            limits: \"tools.limits\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
