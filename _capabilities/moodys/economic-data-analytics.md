---
categories:
- analytics
consumed_apis:
- data-buffet
description: Unified economic data analytics capability combining time series retrieval, basket management, order processing, and data search. Used by economists, risk analysts, and data scientists.
layout: capability
name: Moody's Economic Data Analytics
operations:
- description: Retrieve a time series
  method: GET
  name: get-series
  path: /v1/series
personas: []
provider_name: Moody's
provider_slug: moodys
search_terms:
- list frequencies
- moody's
- create order
- kyc
- check health
- check data buffet api health
- search for available series
- get multi series
- list vintages
- entity verification
- insurance
- delete basket
- list all orders
- delete a basket
- create a new data order
- forecasting
- update basket
- analytics
- list file types
- retrieve a single time series by mnemonic
- get order status and details
- list supported output file types
- download completed order output
- get basket details
- climate risk
- update a basket
- get order
- retrieve a time series
- time series data
- download order
- get basket
- economic data
- list vintages for a series
- get series
- financial analytics
- risk
- retrieve multiple time series
- search series
- credit risk
- screening
- compliance
- create basket
- list orders
- create a new data basket
- list available data frequencies
- list baskets
- list all data baskets
slug: economic-data-analytics
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Moody's Economic Data Analytics\"\n  description: \"Unified economic data analytics capability combining time series retrieval, basket management, order processing, and data search. Used by economists, risk analysts, and data scientists.\"\n  tags: [Moody's, Economic Data, Analytics, Forecasting]\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\nbinds:\n  - namespace: env\n    keys:\n      MOODYS_OAUTH_TOKEN: MOODYS_OAUTH_TOKEN\ncapability:\n  consumes:\n    - import: data-buffet\n      location: ./shared/data-buffet.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: economic-data-analytics-api\n      description: \"Unified REST API for Moody's economic data analytics.\"\n      resources:\n        - path: /v1/series\n          name: series\n          description: \"Time series data\"\n          operations:\n            - { method: GET, name: get-series, description: \"Retrieve a time series\", call: \"data-buffet.get-series\"\
  , outputParameters: [{ type: object, mapping: \"$.\" }] }\n    - type: mcp\n      port: 9090\n      namespace: economic-data-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted economic data analytics.\"\n      tools:\n        - { name: get-series, description: \"Retrieve a single time series by mnemonic\", hints: { readOnly: true }, call: \"data-buffet.get-series\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-multi-series, description: \"Retrieve multiple time series\", hints: { readOnly: true }, call: \"data-buffet.get-multi-series\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: search-series, description: \"Search for available series\", hints: { readOnly: true, openWorld: true }, call: \"data-buffet.search-series\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-baskets, description: \"List all data baskets\", hints: { readOnly: true }, call: \"data-buffet.list-baskets\"\
  , outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-basket, description: \"Create a new data basket\", call: \"data-buffet.create-basket\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-basket, description: \"Get basket details\", hints: { readOnly: true }, call: \"data-buffet.get-basket\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: update-basket, description: \"Update a basket\", call: \"data-buffet.update-basket\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: delete-basket, description: \"Delete a basket\", hints: { destructive: true }, call: \"data-buffet.delete-basket\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-orders, description: \"List all orders\", hints: { readOnly: true }, call: \"data-buffet.list-orders\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-order, description: \"Create\
  \ a new data order\", call: \"data-buffet.create-order\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-order, description: \"Get order status and details\", hints: { readOnly: true }, call: \"data-buffet.get-order\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: download-order, description: \"Download completed order output\", hints: { readOnly: true }, call: \"data-buffet.download-order\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-frequencies, description: \"List available data frequencies\", hints: { readOnly: true }, call: \"data-buffet.list-frequencies\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-vintages, description: \"List vintages for a series\", hints: { readOnly: true }, call: \"data-buffet.list-vintages\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-file-types, description: \"List supported output file\
  \ types\", hints: { readOnly: true }, call: \"data-buffet.list-file-types\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: check-health, description: \"Check Data Buffet API health\", hints: { readOnly: true }, call: \"data-buffet.check-health\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/moodys/refs/heads/main/capabilities/economic-data-analytics.yaml
tags:
- Moody's
- Economic Data
- Analytics
- Forecasting
tools:
- description: Retrieve a single time series by mnemonic
  hints:
    readOnly: true
  name: get-series
- description: Retrieve multiple time series
  hints:
    readOnly: true
  name: get-multi-series
- description: Search for available series
  hints:
    openWorld: true
    readOnly: true
  name: search-series
- description: List all data baskets
  hints:
    readOnly: true
  name: list-baskets
- description: Create a new data basket
  hints: {}
  name: create-basket
- description: Get basket details
  hints:
    readOnly: true
  name: get-basket
- description: Update a basket
  hints: {}
  name: update-basket
- description: Delete a basket
  hints:
    destructive: true
  name: delete-basket
- description: List all orders
  hints:
    readOnly: true
  name: list-orders
- description: Create a new data order
  hints: {}
  name: create-order
- description: Get order status and details
  hints:
    readOnly: true
  name: get-order
- description: Download completed order output
  hints:
    readOnly: true
  name: download-order
- description: List available data frequencies
  hints:
    readOnly: true
  name: list-frequencies
- description: List vintages for a series
  hints:
    readOnly: true
  name: list-vintages
- description: List supported output file types
  hints:
    readOnly: true
  name: list-file-types
- description: Check Data Buffet API health
  hints:
    readOnly: true
  name: check-health
---
