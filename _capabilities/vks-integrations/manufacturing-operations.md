---
categories: []
consumed_apis: []
description: Workflow capability for manufacturing operations teams using VKS work instruction software. Combines work order management, guidebook access, operations tracking, and production data collection into a unified interface for ERP/MES integration, quality management, and floor traceability.
layout: capability
name: VKS Manufacturing Operations Workflow
operations:
- description: List all work orders, optionally filtered by status.
  method: GET
  name: list-work-orders
  path: /v1/work-orders
- description: Create a new work order from an ERP or MES system.
  method: POST
  name: create-work-order
  path: /v1/work-orders
- description: Get work order details.
  method: GET
  name: get-work-order
  path: /v1/work-orders/{work_order_id}
- description: Update work order status or assignment.
  method: PUT
  name: update-work-order
  path: /v1/work-orders/{work_order_id}
- description: List operational steps for a work order.
  method: GET
  name: list-operations
  path: /v1/work-orders/{work_order_id}/operations
- description: List all published guidebooks.
  method: GET
  name: list-guidebooks
  path: /v1/guidebooks
- description: Get guidebook with step-by-step instructions.
  method: GET
  name: get-guidebook
  path: /v1/guidebooks/{guidebook_id}
- description: Retrieve production data, smart form responses, and traceability records.
  method: GET
  name: list-production-data
  path: /v1/production-data
personas: []
provider_name: VKS Integrations
provider_slug: vks-integrations
search_terms:
- list all published vks guidebooks (work instruction manuals). search by name to find instructions for a specific assembly or process.
- get full details for a manufacturing work order including status, assigned worker, quantities, and timestamps.
- list operation steps
- mes
- manufacturing
- quality management
- retrieve production data records for quality management and traceability. includes smart form responses, actual quantities, worker ids, and completion times.
- create a new work order from an erp or mes system.
- get guidebook with step-by-step instructions.
- list production data
- get work order
- update work order
- list work orders
- erp integration
- get work instructions
- work instructions
- update the status of a work order (planned → in_progress → completed) or reassign it to a different worker.
- list operational steps for a work order.
- push a new work order from erp or mes into vks. link it to a guidebook by id, and include part number and expected production quantity.
- retrieve production data, smart form responses, and traceability records.
- create work order
- list work instructions
- update work order status or assignment.
- get production data
- vks
- operations management
- list manufacturing work orders. filter by status (planned, in_progress, completed, on_hold) to find active or completed orders.
- production data and quality records.
- list guidebooks
- list all published guidebooks.
- get a vks guidebook with its complete step-by-step work instructions, smart forms, and media attachments.
- work instruction guidebooks.
- production data
- list operations
- individual work order.
- work order operational steps.
- get work order details.
- individual guidebook.
- work orders
- manufacturing work order management.
- list the operational steps for a work order and their completion status.
- get guidebook
- list all work orders, optionally filtered by status.
- update work order status
slug: manufacturing-operations
source_filename: manufacturing-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: VKS Manufacturing Operations Workflow\n  description: Workflow capability for manufacturing operations teams using VKS work instruction software. Combines work order\n    management, guidebook access, operations tracking, and production data collection into a unified interface for ERP/MES\n    integration, quality management, and floor traceability.\n  tags:\n  - VKS\n  - ERP Integration\n  - Manufacturing\n  - MES\n  - Operations Management\n  - Production Data\n  - Quality Management\n  - Work Instructions\n  - Work Orders\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VKS_API_KEY: VKS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: vks\n    baseUri: https://api.vksapp.com\n    description: VKS manufacturing work instruction and work order API.\n    authentication:\n      type: bearer\n      token: '{{VKS_API_KEY}}'\n    resources:\n    - name: work-orders\n      path: /api/workorders\n\
  \      description: Work order management.\n      operations:\n      - name: list-work-orders\n        method: GET\n        description: List all work orders with optional status and date filtering.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: 'Filter by status: planned, in_progress, completed, on_hold'\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-work-order\n        method: POST\n        description: Create a new work order from ERP/MES.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            work_order_number: '{{tools.work_order_number}}'\n            guidebook_id: '{{tools.guidebook_id}}'\n            part_number: '{{tools.part_number}}'\n            expected_quantity: '{{tools.expected_quantity}}'\n    - name: work-order-detail\n      path: /api/workorders/{work_order_id}\n      description: Individual work order.\n      operations:\n      - name: get-work-order\n        method: GET\n        description: Get full work order details.\n        inputParameters:\n        - name: work_order_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-work-order\n        method: PUT\n        description: Update work order status or assignment.\n        inputParameters:\n        - name: work_order_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            assigned_worker: '{{tools.assigned_worker}}'\n    - name: guidebooks\n      path: /api/guidebooks\n      description: Work instruction guidebook library.\n      operations:\n      - name: list-guidebooks\n        method: GET\n        description: List all published guidebooks.\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: guidebook-detail\n      path: /api/guidebooks/{guidebook_id}\n      description: Individual guidebook.\n      operations:\n      - name: get-guidebook\n  \
  \      method: GET\n        description: Get a guidebook with steps and smart forms.\n        inputParameters:\n        - name: guidebook_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: work-order-operations\n      path: /api/workorders/{work_order_id}/operations\n      description: Operations for a work order.\n      operations:\n      - name: list-work-order-operations\n        method: GET\n        description: List operational steps and their status for a work order.\n        inputParameters:\n        - name: work_order_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: production-data\n      path: /api/production-data\n      description: Production data records.\n\
  \      operations:\n      - name: list-production-data\n        method: GET\n        description: Retrieve production data including smart forms, quality metrics, and traceability.\n        inputParameters:\n        - name: work_order_id\n          in: query\n          type: string\n          required: false\n        - name: from_date\n          in: query\n          type: string\n          required: false\n        - name: to_date\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vks-manufacturing-api\n    description: Unified REST API for VKS manufacturing operations and ERP/MES integration.\n    resources:\n    - path: /v1/work-orders\n      name: work-orders\n      description: Manufacturing\
  \ work order management.\n      operations:\n      - method: GET\n        name: list-work-orders\n        description: List all work orders, optionally filtered by status.\n        call: vks.list-work-orders\n        with:\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-work-order\n        description: Create a new work order from an ERP or MES system.\n        call: vks.create-work-order\n        with:\n          work_order_number: rest.work_order_number\n          guidebook_id: rest.guidebook_id\n          part_number: rest.part_number\n          expected_quantity: rest.expected_quantity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/work-orders/{work_order_id}\n      name: work-order-detail\n      description: Individual work order.\n      operations:\n      - method: GET\n        name: get-work-order\n        description: Get work order details.\n\
  \        call: vks.get-work-order\n        with:\n          work_order_id: rest.work_order_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-work-order\n        description: Update work order status or assignment.\n        call: vks.update-work-order\n        with:\n          work_order_id: rest.work_order_id\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/work-orders/{work_order_id}/operations\n      name: operations\n      description: Work order operational steps.\n      operations:\n      - method: GET\n        name: list-operations\n        description: List operational steps for a work order.\n        call: vks.list-work-order-operations\n        with:\n          work_order_id: rest.work_order_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/guidebooks\n      name: guidebooks\n      description:\
  \ Work instruction guidebooks.\n      operations:\n      - method: GET\n        name: list-guidebooks\n        description: List all published guidebooks.\n        call: vks.list-guidebooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/guidebooks/{guidebook_id}\n      name: guidebook-detail\n      description: Individual guidebook.\n      operations:\n      - method: GET\n        name: get-guidebook\n        description: Get guidebook with step-by-step instructions.\n        call: vks.get-guidebook\n        with:\n          guidebook_id: rest.guidebook_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/production-data\n      name: production-data\n      description: Production data and quality records.\n      operations:\n      - method: GET\n        name: list-production-data\n        description: Retrieve production data, smart form responses, and traceability records.\n        call: vks.list-production-data\n\
  \        with:\n          work_order_id: rest.work_order_id\n          from_date: rest.from_date\n          to_date: rest.to_date\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vks-manufacturing-mcp\n    transport: http\n    description: MCP server for AI-assisted manufacturing operations, ERP integration, and quality traceability.\n    tools:\n    - name: list-work-orders\n      description: List manufacturing work orders. Filter by status (planned, in_progress, completed, on_hold) to find active\n        or completed orders.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vks.list-work-orders\n      with:\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-work-order\n      description: Push a new work order from ERP or MES into VKS. Link it to a guidebook by ID, and include part number and\n        expected production\
  \ quantity.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: vks.create-work-order\n      with:\n        work_order_number: tools.work_order_number\n        guidebook_id: tools.guidebook_id\n        part_number: tools.part_number\n        expected_quantity: tools.expected_quantity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-work-order\n      description: Get full details for a manufacturing work order including status, assigned worker, quantities, and timestamps.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vks.get-work-order\n      with:\n        work_order_id: tools.work_order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-work-order-status\n      description: Update the status of a work order (planned → in_progress → completed) or reassign it to a different worker.\n      hints:\n        readOnly: false\n        idempotent: true\n      call:\
  \ vks.update-work-order\n      with:\n        work_order_id: tools.work_order_id\n        status: tools.status\n        assigned_worker: tools.assigned_worker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-work-instructions\n      description: List all published VKS guidebooks (work instruction manuals). Search by name to find instructions for a\n        specific assembly or process.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vks.list-guidebooks\n      with:\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-work-instructions\n      description: Get a VKS guidebook with its complete step-by-step work instructions, smart forms, and media attachments.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vks.get-guidebook\n      with:\n        guidebook_id: tools.guidebook_id\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: list-operation-steps\n      description: List the operational steps for a work order and their completion status.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vks.list-work-order-operations\n      with:\n        work_order_id: tools.work_order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-production-data\n      description: Retrieve production data records for quality management and traceability. Includes smart form responses,\n        actual quantities, worker IDs, and completion times.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vks.list-production-data\n      with:\n        work_order_id: tools.work_order_id\n        from_date: tools.from_date\n        to_date: tools.to_date\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vks-integrations/refs/heads/main/capabilities/manufacturing-operations.yaml
tags:
- VKS
- ERP Integration
- Manufacturing
- MES
- Operations Management
- Production Data
- Quality Management
- Work Instructions
- Work Orders
tools:
- description: List manufacturing work orders. Filter by status (planned, in_progress, completed, on_hold) to find active or completed orders.
  hints:
    idempotent: true
    readOnly: true
  name: list-work-orders
- description: Push a new work order from ERP or MES into VKS. Link it to a guidebook by ID, and include part number and expected production quantity.
  hints:
    idempotent: false
    readOnly: false
  name: create-work-order
- description: Get full details for a manufacturing work order including status, assigned worker, quantities, and timestamps.
  hints:
    idempotent: true
    readOnly: true
  name: get-work-order
- description: Update the status of a work order (planned → in_progress → completed) or reassign it to a different worker.
  hints:
    idempotent: true
    readOnly: false
  name: update-work-order-status
- description: List all published VKS guidebooks (work instruction manuals). Search by name to find instructions for a specific assembly or process.
  hints:
    idempotent: true
    readOnly: true
  name: list-work-instructions
- description: Get a VKS guidebook with its complete step-by-step work instructions, smart forms, and media attachments.
  hints:
    idempotent: true
    readOnly: true
  name: get-work-instructions
- description: List the operational steps for a work order and their completion status.
  hints:
    idempotent: true
    readOnly: true
  name: list-operation-steps
- description: Retrieve production data records for quality management and traceability. Includes smart form responses, actual quantities, worker IDs, and completion times.
  hints:
    idempotent: true
    readOnly: true
  name: get-production-data
---
