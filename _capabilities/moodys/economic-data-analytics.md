---
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
- get series
- retrieve a single time series by mnemonic
- list vintages for a series
- screening
- analytics
- get basket
- delete a basket
- credit risk
- risk
- update basket
- search for available series
- kyc
- download order
- list frequencies
- entity verification
- delete basket
- list all data baskets
- economic data
- forecasting
- list baskets
- insurance
- list file types
- list orders
- create a new data basket
- search series
- climate risk
- create a new data order
- get basket details
- update a basket
- get order status and details
- moody's
- check health
- download completed order output
- time series data
- list supported output file types
- check data buffet api health
- get order
- retrieve a time series
- retrieve multiple time series
- get multi series
- list vintages
- list all orders
- list available data frequencies
- create basket
- create order
- compliance
- financial analytics
slug: economic-data-analytics
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
