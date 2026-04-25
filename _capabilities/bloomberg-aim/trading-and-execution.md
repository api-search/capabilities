---
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
- route an order to a broker
- get reference data
- portfolio management
- cancel/delete an order
- modify an existing order
- financial data
- get fills
- delete order
- modify order
- get routes from the emsx blotter
- order management
- get orders from the emsx blotter
- market data
- get teams
- route order
- get orders
- get orders from blotter
- bloomberg
- get security reference data for trading
- get routes
- get intraday tick data for a security
- create a trading order
- create a new trading order
- get routes from blotter
- get broker strategies
- trading
- get emsx teams
- get order fills
- get available broker strategies
- create order
- get order and route fills
- get security reference data
- market data for trading decisions
- fill tracking
- get intraday ticks
- route management
- execution management
slug: trading-and-execution
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
