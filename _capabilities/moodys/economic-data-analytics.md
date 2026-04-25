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
- delete a basket
- list baskets
- insurance
- list all orders
- list frequencies
- kyc
- forecasting
- risk
- list supported output file types
- check health
- compliance
- update a basket
- list vintages for a series
- list file types
- retrieve a single time series by mnemonic
- moody's
- get basket details
- download completed order output
- time series data
- entity verification
- create basket
- check data buffet api health
- screening
- update basket
- list orders
- search series
- get order
- financial analytics
- delete basket
- create a new data basket
- retrieve multiple time series
- economic data
- list vintages
- list all data baskets
- climate risk
- credit risk
- create a new data order
- get multi series
- create order
- analytics
- get series
- get order status and details
- download order
- list available data frequencies
- retrieve a time series
- get basket
- search for available series
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
