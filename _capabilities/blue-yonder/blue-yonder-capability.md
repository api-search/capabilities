---
categories: []
consumed_apis: []
description: The Blue Yonder Warehouse Management API provides access to warehouse operations data including inventory positions, task management, labor optimization, and fulfillment workflows. REST APIs support integration with automation systems, robotics, and ERP platforms for distribution center operations.
layout: capability
name: Blue Yonder Warehouse Management API
operations:
- description: List inventory positions
  method: GET
  name: listinventory
  path: /wms/v1/inventory
- description: Get inventory for item
  method: GET
  name: getinventorybyitem
  path: /wms/v1/inventory/{itemId}
- description: List receipts
  method: GET
  name: listreceipts
  path: /wms/v1/receipts
- description: Create inbound receipt
  method: POST
  name: createreceipt
  path: /wms/v1/receipts
- description: List outbound orders
  method: GET
  name: listorders
  path: /wms/v1/orders
- description: Create outbound order
  method: POST
  name: createorder
  path: /wms/v1/orders
- description: List warehouse tasks
  method: GET
  name: listtasks
  path: /wms/v1/tasks
personas: []
provider_name: blue-yonder
provider_slug: blue-yonder
search_terms:
- yonder
- createorder
- listtasks
- blue
- create inbound receipt
- list warehouse tasks
- create outbound order
- list inventory positions
- listreceipts
- createreceipt
- getinventorybyitem
- get inventory for item
- list receipts
- api
- list outbound orders
- listorders
- listinventory
slug: blue-yonder-capability
source_filename: blue-yonder-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Blue Yonder Warehouse Management API\n  description: The Blue Yonder Warehouse Management API provides access to warehouse operations data including inventory positions,\n    task management, labor optimization, and fulfillment workflows. REST APIs support integration with automation systems,\n    robotics, and ERP platforms for distribution center operations.\n  tags:\n  - Blue\n  - Yonder\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: blue-yonder\n    baseUri: https://api.blueyonder.example.com\n    description: Blue Yonder Warehouse Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BLUE_YONDER_TOKEN}}'\n    resources:\n    - name: wms-v1-inventory\n      path: /wms/v1/inventory\n      operations:\n      - name: listinventory\n        method: GET\n        description: List inventory positions\n        inputParameters:\n        - name:\
  \ locationId\n          in: query\n          type: string\n          description: Filter by warehouse location\n        - name: itemId\n          in: query\n          type: string\n          description: Filter by item/SKU identifier\n        - name: status\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wms-v1-inventory-itemid\n      path: /wms/v1/inventory/{itemId}\n      operations:\n      - name: getinventorybyitem\n        method: GET\n        description: Get inventory for item\n        inputParameters:\n        - name: itemId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: wms-v1-receipts\n      path: /wms/v1/receipts\n      operations:\n      - name: listreceipts\n        method: GET\n        description: List receipts\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        - name: fromDate\n          in: query\n          type: string\n        - name: toDate\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createreceipt\n        method: POST\n        description: Create inbound receipt\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wms-v1-orders\n      path: /wms/v1/orders\n      operations:\n      - name: listorders\n        method: GET\n        description: List outbound orders\n        inputParameters:\n        - name: status\n          in: query\n\
  \          type: string\n        - name: priority\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorder\n        method: POST\n        description: Create outbound order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wms-v1-tasks\n      path: /wms/v1/tasks\n      operations:\n      - name: listtasks\n        method: GET\n        description: List warehouse tasks\n        inputParameters:\n        - name: taskType\n          in: query\n          type: string\n        - name: assignedTo\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n \
  \   port: 8080\n    namespace: blue-yonder-rest\n    description: REST adapter for Blue Yonder Warehouse Management API.\n    resources:\n    - path: /wms/v1/inventory\n      name: listinventory\n      operations:\n      - method: GET\n        name: listinventory\n        description: List inventory positions\n        call: blue-yonder.listinventory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wms/v1/inventory/{itemId}\n      name: getinventorybyitem\n      operations:\n      - method: GET\n        name: getinventorybyitem\n        description: Get inventory for item\n        call: blue-yonder.getinventorybyitem\n        with:\n          itemId: rest.itemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wms/v1/receipts\n      name: listreceipts\n      operations:\n      - method: GET\n        name: listreceipts\n        description: List receipts\n        call: blue-yonder.listreceipts\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /wms/v1/receipts\n      name: createreceipt\n      operations:\n      - method: POST\n        name: createreceipt\n        description: Create inbound receipt\n        call: blue-yonder.createreceipt\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wms/v1/orders\n      name: listorders\n      operations:\n      - method: GET\n        name: listorders\n        description: List outbound orders\n        call: blue-yonder.listorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wms/v1/orders\n      name: createorder\n      operations:\n      - method: POST\n        name: createorder\n        description: Create outbound order\n        call: blue-yonder.createorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wms/v1/tasks\n      name: listtasks\n      operations:\n      - method: GET\n        name: listtasks\n\
  \        description: List warehouse tasks\n        call: blue-yonder.listtasks\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: blue-yonder-mcp\n    transport: http\n    description: MCP adapter for Blue Yonder Warehouse Management API for AI agent use.\n    tools:\n    - name: listinventory\n      description: List inventory positions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: blue-yonder.listinventory\n      with:\n        locationId: tools.locationId\n        itemId: tools.itemId\n        status: tools.status\n        page: tools.page\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: locationId\n        type: string\n        description: Filter by warehouse location\n      - name: itemId\n        type: string\n        description: Filter by item/SKU identifier\n      - name: status\n        type: string\n        description: status\n\
  \      - name: page\n        type: integer\n        description: page\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinventorybyitem\n      description: Get inventory for item\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: blue-yonder.getinventorybyitem\n      with:\n        itemId: tools.itemId\n      inputParameters:\n      - name: itemId\n        type: string\n        description: itemId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreceipts\n      description: List receipts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: blue-yonder.listreceipts\n      with:\n        status: tools.status\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      inputParameters:\n      - name: status\n\
  \        type: string\n        description: status\n      - name: fromDate\n        type: string\n        description: fromDate\n      - name: toDate\n        type: string\n        description: toDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createreceipt\n      description: Create inbound receipt\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: blue-yonder.createreceipt\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorders\n      description: List outbound orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: blue-yonder.listorders\n      with:\n        status: tools.status\n        priority: tools.priority\n      inputParameters:\n      - name: status\n        type: string\n        description: status\n      - name: priority\n        type: string\n        description: priority\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createorder\n      description: Create outbound order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: blue-yonder.createorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtasks\n      description: List warehouse tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: blue-yonder.listtasks\n      with:\n        taskType: tools.taskType\n        assignedTo: tools.assignedTo\n        status: tools.status\n      inputParameters:\n      - name: taskType\n        type: string\n        description: taskType\n      - name: assignedTo\n        type: string\n        description: assignedTo\n      - name: status\n        type: string\n        description: status\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BLUE_YONDER_TOKEN: BLUE_YONDER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/blue-yonder/refs/heads/main/capabilities/blue-yonder-capability.yaml
tags:
- Blue
- Yonder
- API
tools:
- description: List inventory positions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinventory
- description: Get inventory for item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinventorybyitem
- description: List receipts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreceipts
- description: Create inbound receipt
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreceipt
- description: List outbound orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorders
- description: Create outbound order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorder
- description: List warehouse tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtasks
---
