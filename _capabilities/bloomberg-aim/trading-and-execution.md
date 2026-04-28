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
- execution management
- get routes from the emsx blotter
- get orders from blotter
- order management
- route order
- get intraday tick data for a security
- get security reference data for trading
- get emsx teams
- market data
- get fills
- bloomberg
- get security reference data
- delete order
- get available broker strategies
- get broker strategies
- get order fills
- route management
- get orders
- get reference data
- get routes
- get intraday ticks
- modify order
- portfolio management
- cancel/delete an order
- get order and route fills
- fill tracking
- financial data
- trading
- create order
- route an order to a broker
- get teams
- create a trading order
- get orders from the emsx blotter
- get routes from blotter
- market data for trading decisions
- modify an existing order
- create a new trading order
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
