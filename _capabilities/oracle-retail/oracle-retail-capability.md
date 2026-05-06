---
categories: []
consumed_apis: []
description: Oracle Retail Merchandising Foundation Cloud Service (RMFCS) provides REST APIs for managing merchandise hierarchies, item setup, purchase orders, cost management, supplier management, and inventory transactions across omnichannel retail operations.
layout: capability
name: Oracle Retail Merchandising Foundation Cloud Service API
operations:
- description: List items
  method: GET
  name: listitems
  path: /items
- description: Create an item
  method: POST
  name: createitem
  path: /items
- description: Get an item
  method: GET
  name: getitem
  path: /items/{item}
- description: Update an item
  method: PUT
  name: updateitem
  path: /items/{item}
- description: List purchase orders
  method: GET
  name: listpurchaseorders
  path: /purchaseorders
- description: Create a purchase order
  method: POST
  name: createpurchaseorder
  path: /purchaseorders
- description: Get a purchase order
  method: GET
  name: getpurchaseorder
  path: /purchaseorders/{orderId}
- description: List suppliers
  method: GET
  name: listsuppliers
  path: /suppliers
- description: Query inventory positions
  method: GET
  name: getinventory
  path: /inventory
personas: []
provider_name: Oracle Retail
provider_slug: oracle-retail
search_terms:
- query inventory positions
- list items
- get an item
- getinventory
- listsuppliers
- retail
- listitems
- omnichannel
- update an item
- create an item
- get a purchase order
- inventory
- merchandising
- list suppliers
- oracle
- api
- getpurchaseorder
- create a purchase order
- point of sale
- getitem
- updateitem
- pricing
- order management
- listpurchaseorders
- list purchase orders
- createitem
- createpurchaseorder
slug: oracle-retail-capability
source_filename: oracle-retail-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Retail Merchandising Foundation Cloud Service API\n  description: Oracle Retail Merchandising Foundation Cloud Service (RMFCS) provides REST APIs for managing merchandise hierarchies,\n    item setup, purchase orders, cost management, supplier management, and inventory transactions across omnichannel retail\n    operations.\n  tags:\n  - Oracle\n  - Retail\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-retail\n    baseUri: https://retail.example.com/MerchServices/MerchRes/v1\n    description: Oracle Retail Merchandising Foundation Cloud Service API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_RETAIL_TOKEN}}'\n    resources:\n    - name: items\n      path: /items\n      operations:\n      - name: listitems\n        method: GET\n        description: List items\n        inputParameters:\n        - name: department\n         \
  \ in: query\n          type: integer\n          description: Filter by department number\n        - name: class\n          in: query\n          type: integer\n          description: Filter by class number\n        - name: subclass\n          in: query\n          type: integer\n          description: Filter by subclass number\n        - name: status\n          in: query\n          type: string\n          description: Filter by item status\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createitem\n        method: POST\n        description: Create an item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: items-item\n      path: /items/{item}\n      operations:\n      - name:\
  \ getitem\n        method: GET\n        description: Get an item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateitem\n        method: PUT\n        description: Update an item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: purchaseorders\n      path: /purchaseorders\n      operations:\n      - name: listpurchaseorders\n        method: GET\n        description: List purchase orders\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by order status\n        - name: supplier\n          in: query\n          type: integer\n          description: Filter by supplier number\n        - name: fromDate\n          in: query\n          type: string\n          description: Filter orders not before this date (YYYY-MM-DD)\n        - name:\
  \ toDate\n          in: query\n          type: string\n          description: Filter orders not after this date (YYYY-MM-DD)\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpurchaseorder\n        method: POST\n        description: Create a purchase order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: purchaseorders-orderid\n      path: /purchaseorders/{orderId}\n      operations:\n      - name: getpurchaseorder\n        method: GET\n        description: Get a purchase order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: suppliers\n      path: /suppliers\n      operations:\n      - name: listsuppliers\n        method: GET\n        description: List suppliers\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory\n      path: /inventory\n      operations:\n      - name: getinventory\n        method: GET\n        description: Query inventory positions\n        inputParameters:\n        - name: item\n          in: query\n          type: string\n          required: true\n          description: Item number\n        - name: location\n          in: query\n          type: integer\n          description: Store or warehouse\
  \ number\n        - name: locationType\n          in: query\n          type: string\n          description: Location type (S=Store, W=Warehouse)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-retail-rest\n    description: REST adapter for Oracle Retail Merchandising Foundation Cloud Service API.\n    resources:\n    - path: /items\n      name: listitems\n      operations:\n      - method: GET\n        name: listitems\n        description: List items\n        call: oracle-retail.listitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /items\n      name: createitem\n      operations:\n      - method: POST\n        name: createitem\n        description: Create an item\n        call: oracle-retail.createitem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /items/{item}\n\
  \      name: getitem\n      operations:\n      - method: GET\n        name: getitem\n        description: Get an item\n        call: oracle-retail.getitem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /items/{item}\n      name: updateitem\n      operations:\n      - method: PUT\n        name: updateitem\n        description: Update an item\n        call: oracle-retail.updateitem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /purchaseorders\n      name: listpurchaseorders\n      operations:\n      - method: GET\n        name: listpurchaseorders\n        description: List purchase orders\n        call: oracle-retail.listpurchaseorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /purchaseorders\n      name: createpurchaseorder\n      operations:\n      - method: POST\n        name: createpurchaseorder\n        description: Create a purchase order\n        call: oracle-retail.createpurchaseorder\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /purchaseorders/{orderId}\n      name: getpurchaseorder\n      operations:\n      - method: GET\n        name: getpurchaseorder\n        description: Get a purchase order\n        call: oracle-retail.getpurchaseorder\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /suppliers\n      name: listsuppliers\n      operations:\n      - method: GET\n        name: listsuppliers\n        description: List suppliers\n        call: oracle-retail.listsuppliers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inventory\n      name: getinventory\n      operations:\n      - method: GET\n        name: getinventory\n        description: Query inventory positions\n        call: oracle-retail.getinventory\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n \
  \   port: 9090\n    namespace: oracle-retail-mcp\n    transport: http\n    description: MCP adapter for Oracle Retail Merchandising Foundation Cloud Service API for AI agent use.\n    tools:\n    - name: listitems\n      description: List items\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-retail.listitems\n      with:\n        department: tools.department\n        class: tools.class\n        subclass: tools.subclass\n        status: tools.status\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: department\n        type: integer\n        description: Filter by department number\n      - name: class\n        type: integer\n        description: Filter by class number\n      - name: subclass\n        type: integer\n        description: Filter by subclass number\n      - name: status\n        type: string\n        description: Filter by item status\n      - name: offset\n      \
  \  type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createitem\n      description: Create an item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-retail.createitem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getitem\n      description: Get an item\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-retail.getitem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateitem\n      description: Update an item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: oracle-retail.updateitem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpurchaseorders\n      description:\
  \ List purchase orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-retail.listpurchaseorders\n      with:\n        status: tools.status\n        supplier: tools.supplier\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by order status\n      - name: supplier\n        type: integer\n        description: Filter by supplier number\n      - name: fromDate\n        type: string\n        description: Filter orders not before this date (YYYY-MM-DD)\n      - name: toDate\n        type: string\n        description: Filter orders not after this date (YYYY-MM-DD)\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: createpurchaseorder\n      description: Create a purchase order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-retail.createpurchaseorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpurchaseorder\n      description: Get a purchase order\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-retail.getpurchaseorder\n      with:\n        orderId: tools.orderId\n      inputParameters:\n      - name: orderId\n        type: integer\n        description: orderId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsuppliers\n      description: List suppliers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-retail.listsuppliers\n      with:\n        status: tools.status\n        offset: tools.offset\n\
  \        limit: tools.limit\n      inputParameters:\n      - name: status\n        type: string\n        description: status\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinventory\n      description: Query inventory positions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-retail.getinventory\n      with:\n        item: tools.item\n        location: tools.location\n        locationType: tools.locationType\n      inputParameters:\n      - name: item\n        type: string\n        description: Item number\n        required: true\n      - name: location\n        type: integer\n        description: Store or warehouse number\n      - name: locationType\n        type: string\n        description: Location type (S=Store, W=Warehouse)\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ORACLE_RETAIL_TOKEN: ORACLE_RETAIL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-retail/refs/heads/main/capabilities/oracle-retail-capability.yaml
tags:
- Oracle
- Retail
- API
tools:
- description: List items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listitems
- description: Create an item
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createitem
- description: Get an item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getitem
- description: Update an item
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateitem
- description: List purchase orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpurchaseorders
- description: Create a purchase order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpurchaseorder
- description: Get a purchase order
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpurchaseorder
- description: List suppliers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsuppliers
- description: Query inventory positions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinventory
---
