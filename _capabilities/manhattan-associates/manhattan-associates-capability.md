---
categories: []
consumed_apis: []
description: Manhattan Active Omni APIs enable omnichannel order management and fulfillment, including order promising, order orchestration, inventory availability, and customer service operations for retail and distribution.
layout: capability
name: Manhattan Active Omni Order Management API
operations:
- description: List orders
  method: GET
  name: listorders
  path: /orders
- description: Create an order
  method: POST
  name: createorder
  path: /orders
- description: Get an order
  method: GET
  name: getorder
  path: /orders/{orderId}
- description: Update an order
  method: PATCH
  name: updateorder
  path: /orders/{orderId}
- description: Cancel an order
  method: POST
  name: cancelorder
  path: /orders/{orderId}/cancel
- description: Check inventory availability
  method: POST
  name: checkinventoryavailability
  path: /inventory/availability
- description: Get inventory positions
  method: GET
  name: getinventorypositions
  path: /inventory/positions
- description: Check order promise (ATP)
  method: POST
  name: checkorderpromise
  path: /promise/check
- description: Create a return
  method: POST
  name: createreturn
  path: /returns
personas: []
provider_name: manhattan-associates
provider_slug: manhattan-associates
search_terms:
- cancelorder
- get inventory positions
- create an order
- api
- check inventory availability
- update an order
- createorder
- get an order
- createreturn
- getorder
- associates
- cancel an order
- check order promise (atp)
- listorders
- list orders
- checkorderpromise
- checkinventoryavailability
- updateorder
- create a return
- manhattan
- getinventorypositions
slug: manhattan-associates-capability
source_filename: manhattan-associates-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Manhattan Active Omni Order Management API\n  description: Manhattan Active Omni APIs enable omnichannel order management and fulfillment, including order promising,\n    order orchestration, inventory availability, and customer service operations for retail and distribution.\n  tags:\n  - Manhattan\n  - Associates\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: manhattan-associates\n    baseUri: https://api.developer.manh.com/omni/v1\n    description: Manhattan Active Omni Order Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MANHATTAN_ASSOCIATES_TOKEN}}'\n    resources:\n    - name: orders\n      path: /orders\n      operations:\n      - name: listorders\n        method: GET\n        description: List orders\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        - name: customerId\n\
  \          in: query\n          type: string\n        - name: channelId\n          in: query\n          type: string\n        - name: orderDateFrom\n          in: query\n          type: string\n        - name: orderDateTo\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorder\n        method: POST\n        description: Create an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders-orderid\n      path: /orders/{orderId}\n      operations:\n      - name: getorder\n        method: GET\n        description: Get an order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateorder\n        method: PATCH\n        description: Update an order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders-orderid-cancel\n      path: /orders/{orderId}/cancel\n      operations:\n      - name: cancelorder\n        method: POST\n        description: Cancel an order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory-availability\n      path: /inventory/availability\n      operations:\n\
  \      - name: checkinventoryavailability\n        method: POST\n        description: Check inventory availability\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory-positions\n      path: /inventory/positions\n      operations:\n      - name: getinventorypositions\n        method: GET\n        description: Get inventory positions\n        inputParameters:\n        - name: itemId\n          in: query\n          type: string\n        - name: locationId\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: promise-check\n      path: /promise/check\n      operations:\n      - name: checkorderpromise\n        method: POST\n        description: Check order promise (ATP)\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: returns\n      path: /returns\n      operations:\n      - name: createreturn\n        method: POST\n        description: Create a return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: manhattan-associates-rest\n    description: REST adapter for Manhattan Active Omni Order Management API.\n    resources:\n    - path: /orders\n      name: listorders\n      operations:\n      - method: GET\n        name: listorders\n        description: List orders\n        call: manhattan-associates.listorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders\n      name: createorder\n      operations:\n      - method: POST\n        name: createorder\n        description: Create an order\n        call: manhattan-associates.createorder\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderId}\n      name: getorder\n      operations:\n      - method: GET\n        name: getorder\n        description: Get an order\n        call: manhattan-associates.getorder\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderId}\n      name: updateorder\n      operations:\n      - method: PATCH\n        name: updateorder\n        description: Update an order\n        call: manhattan-associates.updateorder\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderId}/cancel\n      name: cancelorder\n      operations:\n      - method: POST\n        name: cancelorder\n        description: Cancel an order\n        call: manhattan-associates.cancelorder\n        with:\n          orderId: rest.orderId\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inventory/availability\n      name: checkinventoryavailability\n      operations:\n      - method: POST\n        name: checkinventoryavailability\n        description: Check inventory availability\n        call: manhattan-associates.checkinventoryavailability\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inventory/positions\n      name: getinventorypositions\n      operations:\n      - method: GET\n        name: getinventorypositions\n        description: Get inventory positions\n        call: manhattan-associates.getinventorypositions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /promise/check\n      name: checkorderpromise\n      operations:\n      - method: POST\n        name: checkorderpromise\n        description: Check order promise (ATP)\n        call: manhattan-associates.checkorderpromise\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /returns\n      name: createreturn\n      operations:\n      - method: POST\n        name: createreturn\n        description: Create a return\n        call: manhattan-associates.createreturn\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: manhattan-associates-mcp\n    transport: http\n    description: MCP adapter for Manhattan Active Omni Order Management API for AI agent use.\n    tools:\n    - name: listorders\n      description: List orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: manhattan-associates.listorders\n      with:\n        status: tools.status\n        customerId: tools.customerId\n        channelId: tools.channelId\n        orderDateFrom: tools.orderDateFrom\n        orderDateTo: tools.orderDateTo\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n\
  \      - name: status\n        type: string\n        description: status\n      - name: customerId\n        type: string\n        description: customerId\n      - name: channelId\n        type: string\n        description: channelId\n      - name: orderDateFrom\n        type: string\n        description: orderDateFrom\n      - name: orderDateTo\n        type: string\n        description: orderDateTo\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorder\n      description: Create an order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: manhattan-associates.createorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorder\n      description: Get an order\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: manhattan-associates.getorder\n      with:\n        orderId: tools.orderId\n      inputParameters:\n      - name: orderId\n        type: string\n        description: orderId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateorder\n      description: Update an order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: manhattan-associates.updateorder\n      with:\n        orderId: tools.orderId\n      inputParameters:\n      - name: orderId\n        type: string\n        description: orderId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelorder\n      description: Cancel an order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: manhattan-associates.cancelorder\n      with:\n        orderId: tools.orderId\n  \
  \    inputParameters:\n      - name: orderId\n        type: string\n        description: orderId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: checkinventoryavailability\n      description: Check inventory availability\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: manhattan-associates.checkinventoryavailability\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinventorypositions\n      description: Get inventory positions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: manhattan-associates.getinventorypositions\n      with:\n        itemId: tools.itemId\n        locationId: tools.locationId\n        limit: tools.limit\n      inputParameters:\n      - name: itemId\n        type: string\n        description: itemId\n      - name: locationId\n        type: string\n        description:\
  \ locationId\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: checkorderpromise\n      description: Check order promise (ATP)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: manhattan-associates.checkorderpromise\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createreturn\n      description: Create a return\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: manhattan-associates.createreturn\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MANHATTAN_ASSOCIATES_TOKEN: MANHATTAN_ASSOCIATES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/manhattan-associates/refs/heads/main/capabilities/manhattan-associates-capability.yaml
tags:
- Manhattan
- Associates
- API
tools:
- description: List orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorders
- description: Create an order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorder
- description: Get an order
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorder
- description: Update an order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateorder
- description: Cancel an order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelorder
- description: Check inventory availability
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: checkinventoryavailability
- description: Get inventory positions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinventorypositions
- description: Check order promise (ATP)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: checkorderpromise
- description: Create a return
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreturn
---
