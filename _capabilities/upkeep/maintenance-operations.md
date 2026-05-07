---
categories: []
consumed_apis: []
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
- facility management
- work order management
- parts and inventory
- get asset details and history
- preventive maintenance schedules
- upkeep
- individual work order operations
- meter tracking
- list meters
- create asset
- create a new pm schedule
- register a new asset in the system
- list parts and inventory items
- create a new preventive maintenance schedule
- maintenance management
- asset management
- list maintenance requests
- update a work order status, priority, or assignment
- update work order
- list facility assets, optionally filtered by location
- list preventive maintenances
- preventive maintenance
- individual asset operations
- get details and maintenance history for a specific asset
- list parts
- work orders
- list preventive maintenance schedules
- list parts in inventory
- maintenance request intake
- list work orders
- create work order
- list meters for asset condition tracking
- cmms
- list pm schedules
- create a new maintenance work order
- asset tracking and management
- list work orders with optional filters
- create preventive maintenance
- get work order
- update a work order status or assignment
- create request
- get asset
- register a new asset
- get full details of a specific work order
- get work order details
- list maintenance requests submitted by requestors
- submit a new maintenance request
- list requests
- list maintenance work orders with optional status and priority filters
- submit a maintenance request
- list assets
- list assets with location filter
slug: maintenance-operations
source_filename: maintenance-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: UpKeep Maintenance Operations\n  description: Workflow capability for UpKeep maintenance operations, composing work order management, asset tracking, preventive\n    maintenance scheduling, parts inventory, and purchase order workflows. Designed for maintenance managers, facility managers,\n    and technicians executing day-to-day operations management tasks.\n  tags:\n  - UpKeep\n  - CMMS\n  - Maintenance Management\n  - Asset Management\n  - Facility Management\n  - Work Orders\n  - Preventive Maintenance\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UPKEEP_SESSION_TOKEN: UPKEEP_SESSION_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: upkeep\n    baseUri: https://api.onupkeep.com/api/v2\n    description: UpKeep CMMS REST API\n    authentication:\n      type: apikey\n      key: session-token\n      value: '{{UPKEEP_SESSION_TOKEN}}'\n      placement: header\n    resources:\n \
  \   - name: work-orders\n      path: /work-orders\n      description: Work order management\n      operations:\n      - name: list-work-orders\n        method: GET\n        description: List work orders with optional filters\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: priority\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-work-order\n        method: POST\n        description: Create a new work order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n       \
  \ body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n            priority: '{{tools.priority}}'\n            assetId: '{{tools.assetId}}'\n            locationId: '{{tools.locationId}}'\n            assignedToId: '{{tools.assignedToId}}'\n            dueDate: '{{tools.dueDate}}'\n    - name: work-order\n      path: /work-orders/{id}\n      description: Individual work order operations\n      operations:\n      - name: get-work-order\n        method: GET\n        description: Get work order details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-work-order\n        method: PATCH\n        description: Update a work order\n        inputParameters:\n        - name: id\n          in: path\n     \
  \     type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            priority: '{{tools.priority}}'\n            assignedToId: '{{tools.assignedToId}}'\n    - name: assets\n      path: /assets\n      description: Asset management\n      operations:\n      - name: list-assets\n        method: GET\n        description: List assets\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: locationId\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ create-asset\n        method: POST\n        description: Create a new asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            locationId: '{{tools.locationId}}'\n            serialNumber: '{{tools.serialNumber}}'\n            manufacturer: '{{tools.manufacturer}}'\n            model: '{{tools.model}}'\n    - name: asset\n      path: /assets/{id}\n      description: Individual asset operations\n      operations:\n      - name: get-asset\n        method: GET\n        description: Get asset details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: preventive-maintenances\n      path: /preventive-maintenances\n\
  \      description: Preventive maintenance schedules\n      operations:\n      - name: list-preventive-maintenances\n        method: GET\n        description: List preventive maintenance schedules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-preventive-maintenance\n        method: POST\n        description: Create a preventive maintenance schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            assetId: '{{tools.assetId}}'\n            frequency: '{{tools.frequency}}'\n            startDate: '{{tools.startDate}}'\n    - name: parts\n      path: /parts\n      description: Parts inventory management\n      operations:\n      - name: list-parts\n        method: GET\n        description: List parts in inventory\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meters\n      path: /meters\n      description: Meter management\n      operations:\n      - name: list-meters\n        method: GET\n        description: List meters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: requests\n      path: /requests\n      description: Maintenance request management\n      operations:\n      - name: list-requests\n        method: GET\n        description: List maintenance requests\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-request\n        method: POST\n        description: Submit a maintenance request\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n            assetId: '{{tools.assetId}}'\n            priority: '{{tools.priority}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: upkeep-maintenance-api\n    description: Unified REST API for UpKeep maintenance operations workflows.\n    resources:\n    - path: /v1/work-orders\n      name: work-orders\n      description: Work order management\n      operations:\n      - method: GET\n        name: list-work-orders\n        description: List work orders with optional filters\n        call: upkeep.list-work-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-work-order\n        description: Create a new maintenance work order\n        call:\
  \ upkeep.create-work-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/work-orders/{id}\n      name: work-order\n      description: Individual work order operations\n      operations:\n      - method: GET\n        name: get-work-order\n        description: Get work order details\n        call: upkeep.get-work-order\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-work-order\n        description: Update a work order status or assignment\n        call: upkeep.update-work-order\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Asset tracking and management\n      operations:\n      - method: GET\n        name: list-assets\n        description: List assets with location filter\n        call: upkeep.list-assets\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-asset\n        description: Register a new asset\n        call: upkeep.create-asset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets/{id}\n      name: asset\n      description: Individual asset operations\n      operations:\n      - method: GET\n        name: get-asset\n        description: Get asset details and history\n        call: upkeep.get-asset\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/preventive-maintenances\n      name: preventive-maintenances\n      description: Preventive maintenance schedules\n      operations:\n      - method: GET\n        name: list-preventive-maintenances\n        description: List PM schedules\n        call: upkeep.list-preventive-maintenances\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n      - method: POST\n        name: create-preventive-maintenance\n        description: Create a new PM schedule\n        call: upkeep.create-preventive-maintenance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parts\n      name: parts\n      description: Parts and inventory\n      operations:\n      - method: GET\n        name: list-parts\n        description: List parts in inventory\n        call: upkeep.list-parts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meters\n      name: meters\n      description: Meter tracking\n      operations:\n      - method: GET\n        name: list-meters\n        description: List meters\n        call: upkeep.list-meters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/requests\n      name: requests\n      description: Maintenance request intake\n      operations:\n      - method: GET\n        name: list-requests\n\
  \        description: List maintenance requests\n        call: upkeep.list-requests\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-request\n        description: Submit a maintenance request\n        call: upkeep.create-request\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: upkeep-maintenance-mcp\n    transport: http\n    description: MCP server for AI-assisted UpKeep maintenance operations.\n    tools:\n    - name: list-work-orders\n      description: List maintenance work orders with optional status and priority filters\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upkeep.list-work-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-work-order\n      description: Get full details of a specific work order\n      hints:\n        readOnly: true\n        openWorld: false\n   \
  \   call: upkeep.get-work-order\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-work-order\n      description: Create a new maintenance work order\n      hints:\n        readOnly: false\n        openWorld: false\n      call: upkeep.create-work-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-work-order\n      description: Update a work order status, priority, or assignment\n      hints:\n        readOnly: false\n        idempotent: true\n      call: upkeep.update-work-order\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assets\n      description: List facility assets, optionally filtered by location\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upkeep.list-assets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset\n      description:\
  \ Get details and maintenance history for a specific asset\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upkeep.get-asset\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-asset\n      description: Register a new asset in the system\n      hints:\n        readOnly: false\n        openWorld: false\n      call: upkeep.create-asset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-preventive-maintenances\n      description: List preventive maintenance schedules\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upkeep.list-preventive-maintenances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-preventive-maintenance\n      description: Create a new preventive maintenance schedule\n      hints:\n        readOnly: false\n        openWorld: false\n      call: upkeep.create-preventive-maintenance\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-parts\n      description: List parts and inventory items\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upkeep.list-parts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-meters\n      description: List meters for asset condition tracking\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upkeep.list-meters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-requests\n      description: List maintenance requests submitted by requestors\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upkeep.list-requests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-request\n      description: Submit a new maintenance request\n      hints:\n        readOnly: false\n        openWorld: false\n      call: upkeep.create-request\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
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
