---
api_specs:
- filename: upkeep-openapi.yml
  format: yaml
  label: upkeep
  slug: upkeep
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/upkeep/refs/heads/main/openapi/upkeep-openapi.yml
categories: []
consumed_apis:
- upkeep
description: Workflow capability for UpKeep maintenance operations, composing work order management, asset tracking, preventive maintenance scheduling, parts inventory, and purchase order workflows. Designed for maintenance managers, facility managers, and technicians executing day-to-day operations management tasks.
layout: capability
name: UpKeep Maintenance Operations
operations:
- description: List work orders with optional filters
  method: GET
  name: list-work-orders
  path: /v1/work-orders
- description: Create a new maintenance work order
  method: POST
  name: create-work-order
  path: /v1/work-orders
- description: Get work order details
  method: GET
  name: get-work-order
  path: /v1/work-orders/{id}
- description: Update a work order status or assignment
  method: PATCH
  name: update-work-order
  path: /v1/work-orders/{id}
- description: List assets with location filter
  method: GET
  name: list-assets
  path: /v1/assets
- description: Register a new asset
  method: POST
  name: create-asset
  path: /v1/assets
- description: Get asset details and history
  method: GET
  name: get-asset
  path: /v1/assets/{id}
- description: List PM schedules
  method: GET
  name: list-preventive-maintenances
  path: /v1/preventive-maintenances
- description: Create a new PM schedule
  method: POST
  name: create-preventive-maintenance
  path: /v1/preventive-maintenances
- description: List parts in inventory
  method: GET
  name: list-parts
  path: /v1/parts
- description: List meters
  method: GET
  name: list-meters
  path: /v1/meters
- description: List maintenance requests
  method: GET
  name: list-requests
  path: /v1/requests
- description: Submit a maintenance request
  method: POST
  name: create-request
  path: /v1/requests
personas: []
provider_name: UpKeep
provider_slug: upkeep
search_terms:
- preventive maintenance
- meter tracking
- get asset details and history
- create a new pm schedule
- list maintenance requests submitted by requestors
- submit a maintenance request
- update a work order status or assignment
- list parts
- update work order
- get work order
- asset management
- update a work order status, priority, or assignment
- list maintenance work orders with optional status and priority filters
- list work orders
- list parts in inventory
- create request
- list requests
- upkeep
- list work orders with optional filters
- create preventive maintenance
- create a new preventive maintenance schedule
- list assets with location filter
- submit a new maintenance request
- list pm schedules
- facility management
- maintenance management
- get asset
- parts and inventory
- list preventive maintenances
- preventive maintenance schedules
- get details and maintenance history for a specific asset
- list meters
- list maintenance requests
- register a new asset in the system
- list parts and inventory items
- create a new maintenance work order
- asset tracking and management
- work order management
- get work order details
- create work order
- maintenance request intake
- cmms
- list preventive maintenance schedules
- individual work order operations
- create asset
- individual asset operations
- work orders
- list meters for asset condition tracking
- list facility assets, optionally filtered by location
- get full details of a specific work order
- list assets
- register a new asset
slug: maintenance-operations
source_filename: maintenance-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"UpKeep Maintenance Operations\"\n  description: >-\n    Workflow capability for UpKeep maintenance operations, composing work order\n    management, asset tracking, preventive maintenance scheduling, parts\n    inventory, and purchase order workflows. Designed for maintenance managers,\n    facility managers, and technicians executing day-to-day operations\n    management tasks.\n  tags:\n    - UpKeep\n    - CMMS\n    - Maintenance Management\n    - Asset Management\n    - Facility Management\n    - Work Orders\n    - Preventive Maintenance\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UPKEEP_SESSION_TOKEN: UPKEEP_SESSION_TOKEN\n\ncapability:\n  consumes:\n    - import: upkeep\n      location: ./shared/upkeep.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: upkeep-maintenance-api\n      description: \"Unified REST API for UpKeep maintenance operations\
  \ workflows.\"\n      resources:\n        - path: /v1/work-orders\n          name: work-orders\n          description: \"Work order management\"\n          operations:\n            - method: GET\n              name: list-work-orders\n              description: \"List work orders with optional filters\"\n              call: \"upkeep.list-work-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-work-order\n              description: \"Create a new maintenance work order\"\n              call: \"upkeep.create-work-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/work-orders/{id}\n          name: work-order\n          description: \"Individual work order operations\"\n          operations:\n            - method: GET\n              name: get-work-order\n              description: \"Get work order details\"\
  \n              call: \"upkeep.get-work-order\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-work-order\n              description: \"Update a work order status or assignment\"\n              call: \"upkeep.update-work-order\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/assets\n          name: assets\n          description: \"Asset tracking and management\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List assets with location filter\"\n              call: \"upkeep.list-assets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name:\
  \ create-asset\n              description: \"Register a new asset\"\n              call: \"upkeep.create-asset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/assets/{id}\n          name: asset\n          description: \"Individual asset operations\"\n          operations:\n            - method: GET\n              name: get-asset\n              description: \"Get asset details and history\"\n              call: \"upkeep.get-asset\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/preventive-maintenances\n          name: preventive-maintenances\n          description: \"Preventive maintenance schedules\"\n          operations:\n            - method: GET\n              name: list-preventive-maintenances\n              description: \"List PM schedules\"\n              call: \"upkeep.list-preventive-maintenances\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-preventive-maintenance\n              description: \"Create a new PM schedule\"\n              call: \"upkeep.create-preventive-maintenance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/parts\n          name: parts\n          description: \"Parts and inventory\"\n          operations:\n            - method: GET\n              name: list-parts\n              description: \"List parts in inventory\"\n              call: \"upkeep.list-parts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/meters\n          name: meters\n          description: \"Meter tracking\"\n          operations:\n            - method: GET\n              name: list-meters\n              description: \"List meters\"\
  \n              call: \"upkeep.list-meters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/requests\n          name: requests\n          description: \"Maintenance request intake\"\n          operations:\n            - method: GET\n              name: list-requests\n              description: \"List maintenance requests\"\n              call: \"upkeep.list-requests\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-request\n              description: \"Submit a maintenance request\"\n              call: \"upkeep.create-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: upkeep-maintenance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted UpKeep maintenance operations.\"\
  \n      tools:\n        - name: list-work-orders\n          description: \"List maintenance work orders with optional status and priority filters\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upkeep.list-work-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-work-order\n          description: \"Get full details of a specific work order\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upkeep.get-work-order\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-work-order\n          description: \"Create a new maintenance work order\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"upkeep.create-work-order\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n        - name: update-work-order\n          description: \"Update a work order status, priority, or assignment\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"upkeep.update-work-order\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-assets\n          description: \"List facility assets, optionally filtered by location\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upkeep.list-assets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-asset\n          description: \"Get details and maintenance history for a specific asset\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upkeep.get-asset\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-asset\n          description: \"Register a new asset in the system\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"upkeep.create-asset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-preventive-maintenances\n          description: \"List preventive maintenance schedules\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upkeep.list-preventive-maintenances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-preventive-maintenance\n          description: \"Create a new preventive maintenance schedule\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"upkeep.create-preventive-maintenance\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-parts\n          description: \"List parts and inventory items\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upkeep.list-parts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-meters\n          description: \"List meters for asset condition tracking\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upkeep.list-meters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-requests\n          description: \"List maintenance requests submitted by requestors\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upkeep.list-requests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-request\n          description: \"Submit\
  \ a new maintenance request\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"upkeep.create-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/upkeep/refs/heads/main/capabilities/maintenance-operations.yaml
tags:
- UpKeep
- CMMS
- Maintenance Management
- Asset Management
- Facility Management
- Work Orders
- Preventive Maintenance
tools:
- description: List maintenance work orders with optional status and priority filters
  hints:
    openWorld: false
    readOnly: true
  name: list-work-orders
- description: Get full details of a specific work order
  hints:
    openWorld: false
    readOnly: true
  name: get-work-order
- description: Create a new maintenance work order
  hints:
    openWorld: false
    readOnly: false
  name: create-work-order
- description: Update a work order status, priority, or assignment
  hints:
    idempotent: true
    readOnly: false
  name: update-work-order
- description: List facility assets, optionally filtered by location
  hints:
    openWorld: false
    readOnly: true
  name: list-assets
- description: Get details and maintenance history for a specific asset
  hints:
    openWorld: false
    readOnly: true
  name: get-asset
- description: Register a new asset in the system
  hints:
    openWorld: false
    readOnly: false
  name: create-asset
- description: List preventive maintenance schedules
  hints:
    openWorld: false
    readOnly: true
  name: list-preventive-maintenances
- description: Create a new preventive maintenance schedule
  hints:
    openWorld: false
    readOnly: false
  name: create-preventive-maintenance
- description: List parts and inventory items
  hints:
    openWorld: false
    readOnly: true
  name: list-parts
- description: List meters for asset condition tracking
  hints:
    openWorld: false
    readOnly: true
  name: list-meters
- description: List maintenance requests submitted by requestors
  hints:
    openWorld: false
    readOnly: true
  name: list-requests
- description: Submit a new maintenance request
  hints:
    openWorld: false
    readOnly: false
  name: create-request
---
