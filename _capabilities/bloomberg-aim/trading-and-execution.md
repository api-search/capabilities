---
categories: []
consumed_apis: []
description: Workflow for automated trading combining EMSX order/route management with HTTP API market data for traders and algorithmic trading teams.
layout: capability
name: Bloomberg Trading and Execution
operations:
- description: Create a trading order
  method: POST
  name: create-order
  path: /v1/orders
- description: Get orders from blotter
  method: POST
  name: get-orders
  path: /v1/orders
- description: Route an order to a broker
  method: POST
  name: route-order
  path: /v1/routes
- description: Get routes from blotter
  method: POST
  name: get-routes
  path: /v1/routes
- description: Get order fills
  method: POST
  name: get-fills
  path: /v1/fills
- description: Get security reference data
  method: POST
  name: get-reference-data
  path: /v1/market-data
personas: []
provider_name: Bloomberg AIM
provider_slug: bloomberg-aim
search_terms:
- delete order
- market data
- get intraday ticks
- get security reference data for trading
- get order and route fills
- get routes from the emsx blotter
- portfolio management
- get reference data
- create a trading order
- bloomberg
- get routes from blotter
- cancel/delete an order
- fill tracking
- get intraday tick data for a security
- market data for trading decisions
- get emsx teams
- trading
- get security reference data
- modify order
- get routes
- get broker strategies
- financial data
- get teams
- route an order to a broker
- route order
- create a new trading order
- get orders from blotter
- get fills
- modify an existing order
- route management
- get orders from the emsx blotter
- create order
- execution management
- get available broker strategies
- order management
- get orders
- get order fills
slug: trading-and-execution
source_filename: trading-and-execution.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bloomberg Trading and Execution\n  description: Workflow for automated trading combining EMSX order/route management with HTTP API market data for traders\n    and algorithmic trading teams.\n  tags:\n  - Bloomberg\n  - Trading\n  - Execution Management\n  - Order Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BLOOMBERG_EMSX_TOKEN: BLOOMBERG_EMSX_TOKEN\n    BLOOMBERG_HTTP_USERNAME: BLOOMBERG_HTTP_USERNAME\n    BLOOMBERG_HTTP_PASSWORD: BLOOMBERG_HTTP_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: emsx\n    baseUri: https://localhost:3000\n    description: Bloomberg EMSX API via BLPAPI HTTP bridge\n    authentication:\n      type: bearer\n      token: '{{BLOOMBERG_EMSX_TOKEN}}'\n    resources:\n    - name: orders\n      path: /request/blp/emapisvc\n      description: Order management\n      operations:\n      - name: create-order\n        method: POST\n        description:\
  \ Create a new order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            EMSX_TICKER: '{{tools.ticker}}'\n            EMSX_AMOUNT: '{{tools.amount}}'\n            EMSX_ORDER_TYPE: '{{tools.orderType}}'\n            EMSX_SIDE: '{{tools.side}}'\n            EMSX_TIF: '{{tools.tif}}'\n      - name: modify-order\n        method: POST\n        description: Modify an existing order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-order\n        method: POST\n        description: Delete/cancel an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-orders\n        method: POST\n        description: Get orders from the blotter\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes\n      path: /request/blp/emapisvc\n      description: Route management\n      operations:\n      - name: route-order\n        method: POST\n        description: Route an order to a broker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modify-route\n        method: POST\n        description: Modify a route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-routes\n        method: POST\n        description: Get routes from the blotter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fills\n      path: /request/blp/emapisvc\n      description: Fill tracking\n      operations:\n      - name: get-fills\n\
  \        method: POST\n        description: Get order fills\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: broker-strategies\n      path: /request/blp/emapisvc\n      description: Broker strategy queries\n      operations:\n      - name: get-broker-strategies\n        method: POST\n        description: Get available broker strategies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-broker-strategy-info\n        method: POST\n        description: Get broker strategy details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /request/blp/emapisvc\n      description: Team management\n      operations:\n      - name: get-teams\n        method: POST\n        description: Get EMSX teams\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: http-api\n    baseUri: https://localhost:3000\n    description: Bloomberg HTTP API for reference and historical data\n    authentication:\n      type: basic\n      username: '{{BLOOMBERG_HTTP_USERNAME}}'\n      password: '{{BLOOMBERG_HTTP_PASSWORD}}'\n    resources:\n    - name: request\n      path: /request\n      description: Generic BLPAPI request endpoint\n      operations:\n      - name: send-request\n        method: POST\n        description: Send a BLPAPI request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            service: '{{tools.service}}'\n            operation: '{{tools.operation}}'\n            parameters: '{{tools.parameters}}'\n    - name: reference-data\n      path: /request\n      description: Reference\
  \ data requests\n      operations:\n      - name: get-reference-data\n        method: POST\n        description: Get reference data for securities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            service: //blp/refdata\n            operation: ReferenceDataRequest\n            parameters:\n              securities: '{{tools.securities}}'\n              fields: '{{tools.fields}}'\n    - name: historical-data\n      path: /request\n      description: Historical data requests\n      operations:\n      - name: get-historical-data\n        method: POST\n        description: Get historical end-of-day data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            service: //blp/refdata\n            operation: HistoricalDataRequest\n\
  \            parameters:\n              securities: '{{tools.securities}}'\n              fields: '{{tools.fields}}'\n              startDate: '{{tools.startDate}}'\n              endDate: '{{tools.endDate}}'\n    - name: intraday-data\n      path: /request\n      description: Intraday data requests\n      operations:\n      - name: get-intraday-bars\n        method: POST\n        description: Get intraday bar data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-intraday-ticks\n        method: POST\n        description: Get intraday tick data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: field-search\n      path: /request\n      description: Field discovery\n      operations:\n      - name: search-fields\n        method: POST\n        description: Search available data fields\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-field-info\n        method: POST\n        description: Get field metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instruments\n      path: /request\n      description: Instrument search\n      operations:\n      - name: search-instruments\n        method: POST\n        description: Search for securities and instruments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: trading-api\n    description: Unified REST API for Bloomberg trading and execution.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Order management\n      operations:\n      - method: POST\n        name: create-order\n        description:\
  \ Create a trading order\n        call: emsx.create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: get-orders\n        description: Get orders from blotter\n        call: emsx.get-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/routes\n      name: routes\n      description: Route management\n      operations:\n      - method: POST\n        name: route-order\n        description: Route an order to a broker\n        call: emsx.route-order\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: get-routes\n        description: Get routes from blotter\n        call: emsx.get-routes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fills\n      name: fills\n      description: Fill tracking\n      operations:\n      - method: POST\n        name: get-fills\n        description: Get\
  \ order fills\n        call: emsx.get-fills\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/market-data\n      name: market-data\n      description: Market data for trading decisions\n      operations:\n      - method: POST\n        name: get-reference-data\n        description: Get security reference data\n        call: http-api.get-reference-data\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: trading-mcp\n    transport: http\n    description: MCP server for AI-assisted Bloomberg trading and execution.\n    tools:\n    - name: create-order\n      description: Create a new trading order\n      hints:\n        readOnly: false\n      call: emsx.create-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modify-order\n      description: Modify an existing order\n      hints:\n        readOnly: false\n      call: emsx.modify-order\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: delete-order\n      description: Cancel/delete an order\n      hints:\n        readOnly: false\n        destructive: true\n      call: emsx.delete-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-orders\n      description: Get orders from the EMSX blotter\n      hints:\n        readOnly: true\n      call: emsx.get-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: route-order\n      description: Route an order to a broker\n      hints:\n        readOnly: false\n      call: emsx.route-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-routes\n      description: Get routes from the EMSX blotter\n      hints:\n        readOnly: true\n      call: emsx.get-routes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fills\n      description: Get order and route fills\n      hints:\n     \
  \   readOnly: true\n      call: emsx.get-fills\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-broker-strategies\n      description: Get available broker strategies\n      hints:\n        readOnly: true\n      call: emsx.get-broker-strategies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-teams\n      description: Get EMSX teams\n      hints:\n        readOnly: true\n      call: emsx.get-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-reference-data\n      description: Get security reference data for trading\n      hints:\n        readOnly: true\n      call: http-api.get-reference-data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-intraday-ticks\n      description: Get intraday tick data for a security\n      hints:\n        readOnly: true\n      call: http-api.get-intraday-ticks\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bloomberg-aim/refs/heads/main/capabilities/trading-and-execution.yaml
tags:
- Bloomberg
- Trading
- Execution Management
- Order Management
tools:
- description: Create a new trading order
  hints:
    readOnly: false
  name: create-order
- description: Modify an existing order
  hints:
    readOnly: false
  name: modify-order
- description: Cancel/delete an order
  hints:
    destructive: true
    readOnly: false
  name: delete-order
- description: Get orders from the EMSX blotter
  hints:
    readOnly: true
  name: get-orders
- description: Route an order to a broker
  hints:
    readOnly: false
  name: route-order
- description: Get routes from the EMSX blotter
  hints:
    readOnly: true
  name: get-routes
- description: Get order and route fills
  hints:
    readOnly: true
  name: get-fills
- description: Get available broker strategies
  hints:
    readOnly: true
  name: get-broker-strategies
- description: Get EMSX teams
  hints:
    readOnly: true
  name: get-teams
- description: Get security reference data for trading
  hints:
    readOnly: true
  name: get-reference-data
- description: Get intraday tick data for a security
  hints:
    readOnly: true
  name: get-intraday-ticks
---
