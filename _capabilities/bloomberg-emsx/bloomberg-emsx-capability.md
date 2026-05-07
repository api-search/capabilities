---
categories: []
consumed_apis: []
description: Bloomberg Execution Management System (EMSX) API provides programmatic access to Bloomberg's order and execution management platform. It enables automated order creation, routing, modification, and execution monitoring for equity, fixed income, futures, and options trading across global markets. The API supports order lifecycle management, broker selection, route management, and real-time fill notifications through the Bloomberg Terminal and B-PIPE infrastructure.
layout: capability
name: Bloomberg EMSX Trading API
operations:
- description: Bloomberg EMSX List orders
  method: GET
  name: listorders
  path: /orders
- description: Bloomberg EMSX Create a new order
  method: POST
  name: createorder
  path: /orders
- description: Bloomberg EMSX Get order details
  method: GET
  name: getorder
  path: /orders/{orderSequenceNumber}
- description: Bloomberg EMSX Modify an existing order
  method: PATCH
  name: modifyorder
  path: /orders/{orderSequenceNumber}
- description: Bloomberg EMSX Delete an order
  method: DELETE
  name: deleteorder
  path: /orders/{orderSequenceNumber}
- description: Bloomberg EMSX Create an order and route it simultaneously
  method: POST
  name: createorderandroute
  path: /orders/createAndRoute
- description: Bloomberg EMSX Route multiple orders to a broker
  method: POST
  name: grouprouteorders
  path: /orders/groupRoute
- description: Bloomberg EMSX List routes
  method: GET
  name: listroutes
  path: /routes
- description: Bloomberg EMSX Get route details
  method: GET
  name: getroute
  path: /routes/{routeId}
- description: Bloomberg EMSX Modify an existing route
  method: PATCH
  name: modifyroute
  path: /routes/{routeId}
- description: Bloomberg EMSX Cancel a route
  method: DELETE
  name: cancelroute
  path: /routes/{routeId}
- description: Bloomberg EMSX Create a manual fill
  method: POST
  name: createmanualfill
  path: /routes/manualFill
- description: Bloomberg EMSX List fills
  method: GET
  name: listfills
  path: /fills
- description: Bloomberg EMSX Get fill details
  method: GET
  name: getfill
  path: /fills/{fillId}
- description: Bloomberg EMSX List available brokers
  method: GET
  name: listbrokers
  path: /brokers
- description: Bloomberg EMSX List broker strategies
  method: GET
  name: listbrokerstrategies
  path: /brokers/{brokerCode}/strategies
- description: Bloomberg EMSX List EMSX teams
  method: GET
  name: listteams
  path: /teams
- description: Bloomberg EMSX List available order fields
  method: GET
  name: listorderfields
  path: /fields/order
- description: Bloomberg EMSX List available route fields
  method: GET
  name: listroutefields
  path: /fields/route
personas: []
provider_name: Bloomberg EMSX
provider_slug: bloomberg-emsx
search_terms:
- bloomberg emsx list orders
- bloomberg
- bloomberg emsx get order details
- listbrokers
- bloomberg emsx list available order fields
- bloomberg emsx list available route fields
- grouprouteorders
- bloomberg emsx modify an existing route
- bloomberg emsx create a manual fill
- modifyroute
- getfill
- bloomberg emsx route multiple orders to a broker
- bloomberg emsx list fills
- api
- bloomberg emsx list available brokers
- bloomberg emsx list emsx teams
- listorderfields
- order management
- createorder
- cancelroute
- bloomberg emsx get fill details
- bloomberg emsx list routes
- bloomberg emsx cancel a route
- getorder
- createmanualfill
- bloomberg emsx get route details
- listorders
- listfills
- financial services
- trading
- bloomberg emsx delete an order
- bloomberg emsx list broker strategies
- bloomberg emsx modify an existing order
- bloomberg emsx create a new order
- modifyorder
- emsx
- getroute
- listteams
- listroutefields
- deleteorder
- bloomberg emsx create an order and route it simultaneously
- execution management
- listbrokerstrategies
- listroutes
- createorderandroute
slug: bloomberg-emsx-capability
source_filename: bloomberg-emsx-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bloomberg EMSX Trading API\n  description: Bloomberg Execution Management System (EMSX) API provides programmatic access to Bloomberg's order and execution\n    management platform. It enables automated order creation, routing, modification, and execution monitoring for equity,\n    fixed income, futures, and options trading across global markets. The API supports order lifecycle management, broker\n    selection, route management, and real-time fill notifications through the Bloomberg Terminal and B-PIPE infrastructure.\n  tags:\n  - Bloomberg\n  - Emsx\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bloomberg-emsx\n    baseUri: https://api.bloomberg.com/emsxapi/v1\n    description: Bloomberg EMSX Trading API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BLOOMBERG_EMSX_TOKEN}}'\n    resources:\n    - name: orders\n      path: /orders\n      operations:\n\
  \      - name: listorders\n        method: GET\n        description: Bloomberg EMSX List orders\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter orders by status\n        - name: ticker\n          in: query\n          type: string\n          description: Filter by Bloomberg security ticker\n        - name: side\n          in: query\n          type: string\n          description: Filter by order side\n        - name: fromDate\n          in: query\n          type: string\n          description: Filter orders created on or after this date\n        - name: toDate\n          in: query\n          type: string\n          description: Filter orders created on or before this date\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of orders to return\n        - name: offset\n          in: query\n          type: integer\n          description: Number of orders to skip\
  \ for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorder\n        method: POST\n        description: Bloomberg EMSX Create a new order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders-ordersequencenumber\n      path: /orders/{orderSequenceNumber}\n      operations:\n      - name: getorder\n        method: GET\n        description: Bloomberg EMSX Get order details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modifyorder\n        method: PATCH\n        description: Bloomberg EMSX Modify an existing order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteorder\n        method: DELETE\n   \
  \     description: Bloomberg EMSX Delete an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders-createandroute\n      path: /orders/createAndRoute\n      operations:\n      - name: createorderandroute\n        method: POST\n        description: Bloomberg EMSX Create an order and route it simultaneously\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders-grouproute\n      path: /orders/groupRoute\n      operations:\n      - name: grouprouteorders\n        method: POST\n        description: Bloomberg EMSX Route multiple orders to a broker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes\n      path: /routes\n      operations:\n      - name: listroutes\n        method: GET\n        description: Bloomberg\
  \ EMSX List routes\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter routes by status\n        - name: broker\n          in: query\n          type: string\n          description: Filter by broker code\n        - name: orderSequenceNumber\n          in: query\n          type: integer\n          description: Filter routes by parent order sequence number\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of routes to return\n        - name: offset\n          in: query\n          type: integer\n          description: Number of routes to skip for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes-routeid\n      path: /routes/{routeId}\n      operations:\n      - name: getroute\n        method: GET\n        description: Bloomberg EMSX Get route details\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modifyroute\n        method: PATCH\n        description: Bloomberg EMSX Modify an existing route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancelroute\n        method: DELETE\n        description: Bloomberg EMSX Cancel a route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes-manualfill\n      path: /routes/manualFill\n      operations:\n      - name: createmanualfill\n        method: POST\n        description: Bloomberg EMSX Create a manual fill\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fills\n      path: /fills\n      operations:\n      - name: listfills\n\
  \        method: GET\n        description: Bloomberg EMSX List fills\n        inputParameters:\n        - name: ticker\n          in: query\n          type: string\n          description: Filter fills by Bloomberg security ticker\n        - name: broker\n          in: query\n          type: string\n          description: Filter fills by broker code\n        - name: orderSequenceNumber\n          in: query\n          type: integer\n          description: Filter fills by parent order sequence number\n        - name: routeId\n          in: query\n          type: integer\n          description: Filter fills by route identifier\n        - name: fromDate\n          in: query\n          type: string\n          description: Filter fills on or after this date\n        - name: toDate\n          in: query\n          type: string\n          description: Filter fills on or before this date\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of\
  \ fills to return\n        - name: offset\n          in: query\n          type: integer\n          description: Number of fills to skip for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fills-fillid\n      path: /fills/{fillId}\n      operations:\n      - name: getfill\n        method: GET\n        description: Bloomberg EMSX Get fill details\n        inputParameters:\n        - name: fillId\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier of the fill\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: brokers\n      path: /brokers\n      operations:\n      - name: listbrokers\n        method: GET\n        description: Bloomberg EMSX List available brokers\n        inputParameters:\n        - name: assetClass\n          in: query\n \
  \         type: string\n          description: Filter brokers by asset class\n        - name: ticker\n          in: query\n          type: string\n          description: Bloomberg ticker to find brokers available for a specific security\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: brokers-brokercode-strategies\n      path: /brokers/{brokerCode}/strategies\n      operations:\n      - name: listbrokerstrategies\n        method: GET\n        description: Bloomberg EMSX List broker strategies\n        inputParameters:\n        - name: brokerCode\n          in: path\n          type: string\n          required: true\n          description: Bloomberg broker code\n        - name: assetClass\n          in: query\n          type: string\n          description: Filter strategies by asset class\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n    - name: teams\n      path: /teams\n      operations:\n      - name: listteams\n        method: GET\n        description: Bloomberg EMSX List EMSX teams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fields-order\n      path: /fields/order\n      operations:\n      - name: listorderfields\n        method: GET\n        description: Bloomberg EMSX List available order fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fields-route\n      path: /fields/route\n      operations:\n      - name: listroutefields\n        method: GET\n        description: Bloomberg EMSX List available route fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bloomberg-emsx-rest\n\
  \    description: REST adapter for Bloomberg EMSX Trading API.\n    resources:\n    - path: /orders\n      name: listorders\n      operations:\n      - method: GET\n        name: listorders\n        description: Bloomberg EMSX List orders\n        call: bloomberg-emsx.listorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders\n      name: createorder\n      operations:\n      - method: POST\n        name: createorder\n        description: Bloomberg EMSX Create a new order\n        call: bloomberg-emsx.createorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderSequenceNumber}\n      name: getorder\n      operations:\n      - method: GET\n        name: getorder\n        description: Bloomberg EMSX Get order details\n        call: bloomberg-emsx.getorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderSequenceNumber}\n      name: modifyorder\n\
  \      operations:\n      - method: PATCH\n        name: modifyorder\n        description: Bloomberg EMSX Modify an existing order\n        call: bloomberg-emsx.modifyorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderSequenceNumber}\n      name: deleteorder\n      operations:\n      - method: DELETE\n        name: deleteorder\n        description: Bloomberg EMSX Delete an order\n        call: bloomberg-emsx.deleteorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/createAndRoute\n      name: createorderandroute\n      operations:\n      - method: POST\n        name: createorderandroute\n        description: Bloomberg EMSX Create an order and route it simultaneously\n        call: bloomberg-emsx.createorderandroute\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/groupRoute\n      name: grouprouteorders\n      operations:\n      - method:\
  \ POST\n        name: grouprouteorders\n        description: Bloomberg EMSX Route multiple orders to a broker\n        call: bloomberg-emsx.grouprouteorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes\n      name: listroutes\n      operations:\n      - method: GET\n        name: listroutes\n        description: Bloomberg EMSX List routes\n        call: bloomberg-emsx.listroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes/{routeId}\n      name: getroute\n      operations:\n      - method: GET\n        name: getroute\n        description: Bloomberg EMSX Get route details\n        call: bloomberg-emsx.getroute\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes/{routeId}\n      name: modifyroute\n      operations:\n      - method: PATCH\n        name: modifyroute\n        description: Bloomberg EMSX Modify an existing route\n        call: bloomberg-emsx.modifyroute\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes/{routeId}\n      name: cancelroute\n      operations:\n      - method: DELETE\n        name: cancelroute\n        description: Bloomberg EMSX Cancel a route\n        call: bloomberg-emsx.cancelroute\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes/manualFill\n      name: createmanualfill\n      operations:\n      - method: POST\n        name: createmanualfill\n        description: Bloomberg EMSX Create a manual fill\n        call: bloomberg-emsx.createmanualfill\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fills\n      name: listfills\n      operations:\n      - method: GET\n        name: listfills\n        description: Bloomberg EMSX List fills\n        call: bloomberg-emsx.listfills\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fills/{fillId}\n      name: getfill\n\
  \      operations:\n      - method: GET\n        name: getfill\n        description: Bloomberg EMSX Get fill details\n        call: bloomberg-emsx.getfill\n        with:\n          fillId: rest.fillId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /brokers\n      name: listbrokers\n      operations:\n      - method: GET\n        name: listbrokers\n        description: Bloomberg EMSX List available brokers\n        call: bloomberg-emsx.listbrokers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /brokers/{brokerCode}/strategies\n      name: listbrokerstrategies\n      operations:\n      - method: GET\n        name: listbrokerstrategies\n        description: Bloomberg EMSX List broker strategies\n        call: bloomberg-emsx.listbrokerstrategies\n        with:\n          brokerCode: rest.brokerCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams\n      name: listteams\n\
  \      operations:\n      - method: GET\n        name: listteams\n        description: Bloomberg EMSX List EMSX teams\n        call: bloomberg-emsx.listteams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fields/order\n      name: listorderfields\n      operations:\n      - method: GET\n        name: listorderfields\n        description: Bloomberg EMSX List available order fields\n        call: bloomberg-emsx.listorderfields\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fields/route\n      name: listroutefields\n      operations:\n      - method: GET\n        name: listroutefields\n        description: Bloomberg EMSX List available route fields\n        call: bloomberg-emsx.listroutefields\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bloomberg-emsx-mcp\n    transport: http\n    description: MCP adapter for Bloomberg EMSX Trading\
  \ API for AI agent use.\n    tools:\n    - name: listorders\n      description: Bloomberg EMSX List orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-emsx.listorders\n      with:\n        status: tools.status\n        ticker: tools.ticker\n        side: tools.side\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter orders by status\n      - name: ticker\n        type: string\n        description: Filter by Bloomberg security ticker\n      - name: side\n        type: string\n        description: Filter by order side\n      - name: fromDate\n        type: string\n        description: Filter orders created on or after this date\n      - name: toDate\n        type: string\n        description: Filter orders created on or before this date\n      - name: limit\n\
  \        type: integer\n        description: Maximum number of orders to return\n      - name: offset\n        type: integer\n        description: Number of orders to skip for pagination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorder\n      description: Bloomberg EMSX Create a new order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-emsx.createorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorder\n      description: Bloomberg EMSX Get order details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-emsx.getorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modifyorder\n      description: Bloomberg EMSX Modify an existing order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ bloomberg-emsx.modifyorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteorder\n      description: Bloomberg EMSX Delete an order\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: bloomberg-emsx.deleteorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorderandroute\n      description: Bloomberg EMSX Create an order and route it simultaneously\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-emsx.createorderandroute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: grouprouteorders\n      description: Bloomberg EMSX Route multiple orders to a broker\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-emsx.grouprouteorders\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: listroutes\n      description: Bloomberg EMSX List routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-emsx.listroutes\n      with:\n        status: tools.status\n        broker: tools.broker\n        orderSequenceNumber: tools.orderSequenceNumber\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter routes by status\n      - name: broker\n        type: string\n        description: Filter by broker code\n      - name: orderSequenceNumber\n        type: integer\n        description: Filter routes by parent order sequence number\n      - name: limit\n        type: integer\n        description: Maximum number of routes to return\n      - name: offset\n        type: integer\n        description: Number of routes to skip for pagination\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: getroute\n      description: Bloomberg EMSX Get route details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-emsx.getroute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modifyroute\n      description: Bloomberg EMSX Modify an existing route\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bloomberg-emsx.modifyroute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelroute\n      description: Bloomberg EMSX Cancel a route\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: bloomberg-emsx.cancelroute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmanualfill\n      description: Bloomberg EMSX Create a manual fill\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: bloomberg-emsx.createmanualfill\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfills\n      description: Bloomberg EMSX List fills\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-emsx.listfills\n      with:\n        ticker: tools.ticker\n        broker: tools.broker\n        orderSequenceNumber: tools.orderSequenceNumber\n        routeId: tools.routeId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: ticker\n        type: string\n        description: Filter fills by Bloomberg security ticker\n      - name: broker\n        type: string\n        description: Filter fills by broker code\n      - name: orderSequenceNumber\n        type: integer\n        description: Filter fills by parent order sequence number\n      - name: routeId\n        type: integer\n\
  \        description: Filter fills by route identifier\n      - name: fromDate\n        type: string\n        description: Filter fills on or after this date\n      - name: toDate\n        type: string\n        description: Filter fills on or before this date\n      - name: limit\n        type: integer\n        description: Maximum number of fills to return\n      - name: offset\n        type: integer\n        description: Number of fills to skip for pagination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfill\n      description: Bloomberg EMSX Get fill details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-emsx.getfill\n      with:\n        fillId: tools.fillId\n      inputParameters:\n      - name: fillId\n        type: integer\n        description: Unique identifier of the fill\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ listbrokers\n      description: Bloomberg EMSX List available brokers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-emsx.listbrokers\n      with:\n        assetClass: tools.assetClass\n        ticker: tools.ticker\n      inputParameters:\n      - name: assetClass\n        type: string\n        description: Filter brokers by asset class\n      - name: ticker\n        type: string\n        description: Bloomberg ticker to find brokers available for a specific security\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbrokerstrategies\n      description: Bloomberg EMSX List broker strategies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-emsx.listbrokerstrategies\n      with:\n        brokerCode: tools.brokerCode\n        assetClass: tools.assetClass\n      inputParameters:\n      - name: brokerCode\n        type: string\n\
  \        description: Bloomberg broker code\n        required: true\n      - name: assetClass\n        type: string\n        description: Filter strategies by asset class\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listteams\n      description: Bloomberg EMSX List EMSX teams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-emsx.listteams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorderfields\n      description: Bloomberg EMSX List available order fields\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bloomberg-emsx.listorderfields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroutefields\n      description: Bloomberg EMSX List available route fields\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ bloomberg-emsx.listroutefields\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BLOOMBERG_EMSX_TOKEN: BLOOMBERG_EMSX_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bloomberg-emsx/refs/heads/main/capabilities/bloomberg-emsx-capability.yaml
tags:
- Bloomberg
- Emsx
- API
tools:
- description: Bloomberg EMSX List orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorders
- description: Bloomberg EMSX Create a new order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorder
- description: Bloomberg EMSX Get order details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorder
- description: Bloomberg EMSX Modify an existing order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: modifyorder
- description: Bloomberg EMSX Delete an order
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteorder
- description: Bloomberg EMSX Create an order and route it simultaneously
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorderandroute
- description: Bloomberg EMSX Route multiple orders to a broker
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: grouprouteorders
- description: Bloomberg EMSX List routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroutes
- description: Bloomberg EMSX Get route details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroute
- description: Bloomberg EMSX Modify an existing route
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: modifyroute
- description: Bloomberg EMSX Cancel a route
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancelroute
- description: Bloomberg EMSX Create a manual fill
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmanualfill
- description: Bloomberg EMSX List fills
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfills
- description: Bloomberg EMSX Get fill details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfill
- description: Bloomberg EMSX List available brokers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbrokers
- description: Bloomberg EMSX List broker strategies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbrokerstrategies
- description: Bloomberg EMSX List EMSX teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listteams
- description: Bloomberg EMSX List available order fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorderfields
- description: Bloomberg EMSX List available route fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroutefields
---
