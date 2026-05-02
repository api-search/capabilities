---
categories: []
consumed_apis:
- emsx
- http-api
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
- create order
- create a trading order
- get emsx teams
- trading
- get intraday tick data for a security
- cancel/delete an order
- market data
- portfolio management
- order management
- fill tracking
- get order fills
- get security reference data for trading
- bloomberg
- execution management
- route management
- get order and route fills
- get orders
- modify order
- get orders from the emsx blotter
- get fills
- get orders from blotter
- modify an existing order
- financial data
- market data for trading decisions
- get teams
- get routes from the emsx blotter
- get reference data
- get available broker strategies
- get routes
- get security reference data
- get intraday ticks
- create a new trading order
- route order
- delete order
- route an order to a broker
- get routes from blotter
- get broker strategies
slug: trading-and-execution
source_filename: trading-and-execution.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Bloomberg Trading and Execution\"\n  description: \"Workflow for automated trading combining EMSX order/route management with HTTP API market data for traders and algorithmic trading teams.\"\n  tags:\n    - Bloomberg\n    - Trading\n    - Execution Management\n    - Order Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      BLOOMBERG_EMSX_TOKEN: BLOOMBERG_EMSX_TOKEN\n      BLOOMBERG_HTTP_USERNAME: BLOOMBERG_HTTP_USERNAME\n      BLOOMBERG_HTTP_PASSWORD: BLOOMBERG_HTTP_PASSWORD\n\ncapability:\n  consumes:\n    - import: emsx\n      location: ./shared/emsx.yaml\n    - import: http-api\n      location: ./shared/http-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: trading-api\n      description: \"Unified REST API for Bloomberg trading and execution.\"\n      resources:\n        - path: /v1/orders\n          name: orders\n          description:\
  \ \"Order management\"\n          operations:\n            - method: POST\n              name: create-order\n              description: \"Create a trading order\"\n              call: \"emsx.create-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: get-orders\n              description: \"Get orders from blotter\"\n              call: \"emsx.get-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/routes\n          name: routes\n          description: \"Route management\"\n          operations:\n            - method: POST\n              name: route-order\n              description: \"Route an order to a broker\"\n              call: \"emsx.route-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: get-routes\n\
  \              description: \"Get routes from blotter\"\n              call: \"emsx.get-routes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/fills\n          name: fills\n          description: \"Fill tracking\"\n          operations:\n            - method: POST\n              name: get-fills\n              description: \"Get order fills\"\n              call: \"emsx.get-fills\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/market-data\n          name: market-data\n          description: \"Market data for trading decisions\"\n          operations:\n            - method: POST\n              name: get-reference-data\n              description: \"Get security reference data\"\n              call: \"http-api.get-reference-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type:\
  \ mcp\n      port: 9091\n      namespace: trading-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Bloomberg trading and execution.\"\n      tools:\n        - name: create-order\n          description: \"Create a new trading order\"\n          hints:\n            readOnly: false\n          call: \"emsx.create-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: modify-order\n          description: \"Modify an existing order\"\n          hints:\n            readOnly: false\n          call: \"emsx.modify-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-order\n          description: \"Cancel/delete an order\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"emsx.delete-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-orders\n\
  \          description: \"Get orders from the EMSX blotter\"\n          hints:\n            readOnly: true\n          call: \"emsx.get-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: route-order\n          description: \"Route an order to a broker\"\n          hints:\n            readOnly: false\n          call: \"emsx.route-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-routes\n          description: \"Get routes from the EMSX blotter\"\n          hints:\n            readOnly: true\n          call: \"emsx.get-routes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-fills\n          description: \"Get order and route fills\"\n          hints:\n            readOnly: true\n          call: \"emsx.get-fills\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: get-broker-strategies\n          description: \"Get available broker strategies\"\n          hints:\n            readOnly: true\n          call: \"emsx.get-broker-strategies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-teams\n          description: \"Get EMSX teams\"\n          hints:\n            readOnly: true\n          call: \"emsx.get-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-reference-data\n          description: \"Get security reference data for trading\"\n          hints:\n            readOnly: true\n          call: \"http-api.get-reference-data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-intraday-ticks\n          description: \"Get intraday tick data for a security\"\n          hints:\n            readOnly: true\n          call: \"http-api.get-intraday-ticks\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
