---
categories: []
consumed_apis: []
description: This is a template APIs.json for a orders API, to be used in storytelling, training, and knowledge bases.
layout: capability
name: Orders API
operations:
- description: Retrieves Orders
  method: GET
  name: getorders
  path: /orders
- description: Orders Create Order
  method: POST
  name: createorder
  path: /orders
- description: Orders Retrieve Order
  method: GET
  name: getorder
  path: /orders/{orderId}
- description: Orders Update Order
  method: PUT
  name: updateorder
  path: /orders/{orderId}
- description: Orders Delete Order
  method: DELETE
  name: deleteorder
  path: /orders/{orderId}
- description: Orders Cancel Order
  method: PUT
  name: sendorder
  path: /orders/{orderId}/cancle
personas: []
provider_name: Orders
provider_slug: api-evangelist-orders
search_terms:
- getorders
- createorder
- orders update order
- deleteorder
- sendorder
- application programming interface
- getorder
- orders cancel order
- orders create order
- api
- orders retrieve order
- retrieves orders
- updateorder
- orders
- orders delete order
slug: orders-api-capability
source_filename: orders-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Orders API\n  description: This is a template APIs.json for a orders API, to be used in storytelling, training, and knowledge bases.\n  tags:\n  - Orders\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: orders-api\n    baseUri: https://api.example.com\n    description: Orders API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: api-key\n      value: '{{ORDERS_API_TOKEN}}'\n    resources:\n    - name: orders\n      path: /orders\n      operations:\n      - name: getorders\n        method: GET\n        description: Retrieves Orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorder\n        method: POST\n        description: Orders Create Order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: orders-orderid\n      path: /orders/{orderId}\n      operations:\n      - name: getorder\n        method: GET\n        description: Orders Retrieve Order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateorder\n        method: PUT\n        description: Orders Update Order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteorder\n        method: DELETE\n        description: Orders Delete Order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders-orderid-cancle\n      path: /orders/{orderId}/cancle\n      operations:\n      - name: sendorder\n        method: PUT\n        description: Orders Cancel Order\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: orders-api-rest\n    description: REST adapter for Orders API.\n    resources:\n    - path: /orders\n      name: getorders\n      operations:\n      - method: GET\n        name: getorders\n        description: Retrieves Orders\n        call: orders-api.getorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders\n      name: createorder\n      operations:\n      - method: POST\n        name: createorder\n        description: Orders Create Order\n        call: orders-api.createorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderId}\n      name: getorder\n      operations:\n      - method: GET\n        name: getorder\n        description: Orders Retrieve Order\n        call: orders-api.getorder\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /orders/{orderId}\n      name: updateorder\n      operations:\n      - method: PUT\n        name: updateorder\n        description: Orders Update Order\n        call: orders-api.updateorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderId}\n      name: deleteorder\n      operations:\n      - method: DELETE\n        name: deleteorder\n        description: Orders Delete Order\n        call: orders-api.deleteorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderId}/cancle\n      name: sendorder\n      operations:\n      - method: PUT\n        name: sendorder\n        description: Orders Cancel Order\n        call: orders-api.sendorder\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: orders-api-mcp\n    transport: http\n    description: MCP adapter for Orders API for AI agent use.\n    tools:\n\
  \    - name: getorders\n      description: Retrieves Orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orders-api.getorders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorder\n      description: Orders Create Order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orders-api.createorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorder\n      description: Orders Retrieve Order\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orders-api.getorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateorder\n      description: Orders Update Order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: orders-api.updateorder\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n    - name: deleteorder\n      description: Orders Delete Order\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: orders-api.deleteorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendorder\n      description: Orders Cancel Order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: orders-api.sendorder\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ORDERS_API_TOKEN: ORDERS_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/api-evangelist-orders/refs/heads/main/capabilities/orders-api-capability.yaml
tags:
- Orders
- Api
- API
tools:
- description: Retrieves Orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorders
- description: Orders Create Order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorder
- description: Orders Retrieve Order
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorder
- description: Orders Update Order
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateorder
- description: Orders Delete Order
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteorder
- description: Orders Cancel Order
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sendorder
---
