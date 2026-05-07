---
categories:
- analytics
consumed_apis: []
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
- analytics
- moody's
- retrieve a single time series by mnemonic
- search for available series
- kyc
- create order
- list file types
- list all orders
- search series
- screening
- download completed order output
- list vintages for a series
- list supported output file types
- create a new data order
- delete basket
- financial analytics
- compliance
- check data buffet api health
- entity verification
- list frequencies
- credit risk
- forecasting
- check health
- delete a basket
- list orders
- list vintages
- update a basket
- get basket details
- list available data frequencies
- risk
- time series data
- economic data
- get series
- climate risk
- get order status and details
- retrieve multiple time series
- create a new data basket
- retrieve a time series
- list all data baskets
- update basket
- insurance
- create basket
- get basket
- download order
- list baskets
- get order
- get multi series
slug: economic-data-analytics
source_filename: economic-data-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Moody's Economic Data Analytics\n  description: Unified economic data analytics capability combining time series retrieval, basket management, order processing,\n    and data search. Used by economists, risk analysts, and data scientists.\n  tags:\n  - Moody's\n  - Economic Data\n  - Analytics\n  - Forecasting\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MOODYS_OAUTH_TOKEN: MOODYS_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: data-buffet\n    baseUri: https://api.economy.com/data/v1\n    description: Data Buffet API for time series retrieval, basket management, and data search.\n    authentication:\n      type: bearer\n      token: '{{MOODYS_OAUTH_TOKEN}}'\n    resources:\n    - name: series\n      path: /series\n      description: Time series operations\n      operations:\n      - name: get-series\n        method: GET\n        description: Retrieve a single time series\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-multi-series\n        method: POST\n        description: Retrieve multiple time series\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-series\n        method: GET\n        description: Search for available series\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: baskets\n      path: /baskets\n      description: Basket management\n      operations:\n      - name: list-baskets\n        method: GET\n        description: List all baskets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-basket\n        method: POST\n        description: Create a new basket\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-basket\n        method: GET\n        description: Get basket details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-basket\n        method: PUT\n        description: Update a basket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-basket\n        method: DELETE\n        description: Delete a basket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Order management\n      operations:\n      - name: list-orders\n        method: GET\n        description: List all orders\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: Create a new order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Get order details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: download-order\n        method: GET\n        description: Download order output\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reference\n      path: /\n      description: Reference data\n      operations:\n      - name: list-frequencies\n        method: GET\n        description: List available frequencies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: list-vintages\n        method: GET\n        description: List vintages for a series\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-file-types\n        method: GET\n        description: List supported file types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: check-health\n        method: GET\n        description: Check service health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: economic-data-analytics-api\n    description: Unified REST API for Moody's economic data analytics.\n    resources:\n    - path: /v1/series\n      name: series\n      description: Time series data\n      operations:\n     \
  \ - method: GET\n        name: get-series\n        description: Retrieve a time series\n        call: data-buffet.get-series\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: economic-data-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted economic data analytics.\n    tools:\n    - name: get-series\n      description: Retrieve a single time series by mnemonic\n      hints:\n        readOnly: true\n      call: data-buffet.get-series\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-multi-series\n      description: Retrieve multiple time series\n      hints:\n        readOnly: true\n      call: data-buffet.get-multi-series\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-series\n      description: Search for available series\n      hints:\n        readOnly: true\n        openWorld: true\n      call: data-buffet.search-series\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-baskets\n      description: List all data baskets\n      hints:\n        readOnly: true\n      call: data-buffet.list-baskets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-basket\n      description: Create a new data basket\n      call: data-buffet.create-basket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-basket\n      description: Get basket details\n      hints:\n        readOnly: true\n      call: data-buffet.get-basket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-basket\n      description: Update a basket\n      call: data-buffet.update-basket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-basket\n      description: Delete a basket\n      hints:\n        destructive: true\n      call: data-buffet.delete-basket\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List all orders\n      hints:\n        readOnly: true\n      call: data-buffet.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-order\n      description: Create a new data order\n      call: data-buffet.create-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get order status and details\n      hints:\n        readOnly: true\n      call: data-buffet.get-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: download-order\n      description: Download completed order output\n      hints:\n        readOnly: true\n      call: data-buffet.download-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-frequencies\n      description: List available data frequencies\n      hints:\n        readOnly: true\n      call: data-buffet.list-frequencies\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vintages\n      description: List vintages for a series\n      hints:\n        readOnly: true\n      call: data-buffet.list-vintages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-file-types\n      description: List supported output file types\n      hints:\n        readOnly: true\n      call: data-buffet.list-file-types\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-health\n      description: Check Data Buffet API health\n      hints:\n        readOnly: true\n      call: data-buffet.check-health\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
