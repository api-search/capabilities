---
categories: []
consumed_apis:
- spg-commodity-insights
description: Commodity market data workflow combining real-time and historical price assessments, symbol discovery, and incremental data sync from S&P Global Commodity Insights (Platts). Used by energy traders, analysts, risk managers, and quant teams.
layout: capability
name: S&P Global Commodity Market Data
operations:
- description: Get current price assessments for specified commodity symbols
  method: GET
  name: get-current-prices
  path: /v1/prices/current
- description: Get historical price assessments over a date range
  method: GET
  name: get-price-history
  path: /v1/prices/history
- description: List available commodity symbols with metadata
  method: GET
  name: list-symbols
  path: /v1/symbols
- description: Get symbols modified since a date for incremental sync
  method: GET
  name: get-modified-symbols
  path: /v1/symbols/modified
personas: []
provider_name: S&P Global
provider_slug: s-and-p-global
search_terms:
- list symbols
- list commodity symbols
- energy markets
- get modified symbols
- market data
- commodity insights
- get price history
- get historical commodity prices
- capital markets
- commodity symbol reference data
- get current commodity prices
- analytics
- get current prices
- financial data
- get current price assessments for specified commodity symbols
- current commodity price assessments
- symbols modified since a date
- get historical price assessments over a date range
- get modified commodity symbols
- fortune 500
- list available commodity symbols with metadata
- get the latest price assessments for platts commodity symbols (e.g., pcaas00 for dated brent crude oil). returns current value, unit of measure, currency, and assessment date.
- get list of commodity symbols with updated price assessments since a given date. use for incremental data sync to keep commodity price databases current.
- s&p global
- trading
- get historical commodity price assessments for a date range. use for time series analysis, backtesting, and trend analysis in energy and commodity markets.
- historical commodity price assessments
- market intelligence
- list available platts commodity symbols with descriptions, units, and assessment frequency. filter by commodity name (crude oil, natural gas, lng, etc.).
- get symbols modified since a date for incremental sync
- credit ratings
slug: commodity-market-data
source_filename: commodity-market-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"S&P Global Commodity Market Data\"\n  description: \"Commodity market data workflow combining real-time and historical price assessments, symbol discovery, and incremental data sync from S&P Global Commodity Insights (Platts). Used by energy traders, analysts, risk managers, and quant teams.\"\n  tags:\n    - S&P Global\n    - Commodity Insights\n    - Energy Markets\n    - Market Data\n    - Trading\n    - Analytics\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPG_CI_ACCESS_TOKEN: SPG_CI_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: spg-commodity-insights\n      location: ./shared/commodity-insights.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: commodity-market-data-api\n      description: \"Unified REST API for S&P Global commodity market data access.\"\n      resources:\n        - path: /v1/prices/current\n          name: current-prices\n\
  \          description: \"Current commodity price assessments\"\n          operations:\n            - method: GET\n              name: get-current-prices\n              description: \"Get current price assessments for specified commodity symbols\"\n              call: \"spg-commodity-insights.get-current-market-data\"\n              with:\n                symbol: \"rest.symbol\"\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/prices/history\n          name: price-history\n          description: \"Historical commodity price assessments\"\n          operations:\n            - method: GET\n              name: get-price-history\n              description: \"Get historical price assessments over a date range\"\n              call: \"spg-commodity-insights.get-historical-market-data\"\n              with:\n                symbol: \"rest.symbol\"\n                startDate: \"rest.startDate\"\
  \n                endDate: \"rest.endDate\"\n                pageSize: \"rest.pageSize\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/symbols\n          name: symbols\n          description: \"Commodity symbol reference data\"\n          operations:\n            - method: GET\n              name: list-symbols\n              description: \"List available commodity symbols with metadata\"\n              call: \"spg-commodity-insights.list-symbols\"\n              with:\n                commodityName: \"rest.commodityName\"\n                assessmentFrequency: \"rest.assessmentFrequency\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/symbols/modified\n          name: modified-symbols\n          description: \"Symbols modified since a date\"\n          operations:\n            - method: GET\n           \
  \   name: get-modified-symbols\n              description: \"Get symbols modified since a date for incremental sync\"\n              call: \"spg-commodity-insights.get-modified-symbols\"\n              with:\n                modifiedDate: \"rest.modifiedDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: commodity-market-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted commodity market data analysis and energy market research.\"\n      tools:\n        - name: get-current-commodity-prices\n          description: \"Get the latest price assessments for Platts commodity symbols (e.g., PCAAS00 for Dated Brent crude oil). Returns current value, unit of measure, currency, and assessment date.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spg-commodity-insights.get-current-market-data\"\n          with:\n\
  \            symbol: \"tools.symbol\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-historical-commodity-prices\n          description: \"Get historical commodity price assessments for a date range. Use for time series analysis, backtesting, and trend analysis in energy and commodity markets.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spg-commodity-insights.get-historical-market-data\"\n          with:\n            symbol: \"tools.symbol\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            pageSize: \"tools.pageSize\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-commodity-symbols\n          description: \"List available Platts commodity symbols with descriptions, units, and assessment frequency. Filter by commodity name (Crude Oil,\
  \ Natural Gas, LNG, etc.).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spg-commodity-insights.list-symbols\"\n          with:\n            commodityName: \"tools.commodityName\"\n            assessmentFrequency: \"tools.assessmentFrequency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-modified-commodity-symbols\n          description: \"Get list of commodity symbols with updated price assessments since a given date. Use for incremental data sync to keep commodity price databases current.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spg-commodity-insights.get-modified-symbols\"\n          with:\n            modifiedDate: \"tools.modifiedDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/s-and-p-global/refs/heads/main/capabilities/commodity-market-data.yaml
tags:
- S&P Global
- Commodity Insights
- Energy Markets
- Market Data
- Trading
- Analytics
tools:
- description: Get the latest price assessments for Platts commodity symbols (e.g., PCAAS00 for Dated Brent crude oil). Returns current value, unit of measure, currency, and assessment date.
  hints:
    openWorld: false
    readOnly: true
  name: get-current-commodity-prices
- description: Get historical commodity price assessments for a date range. Use for time series analysis, backtesting, and trend analysis in energy and commodity markets.
  hints:
    openWorld: false
    readOnly: true
  name: get-historical-commodity-prices
- description: List available Platts commodity symbols with descriptions, units, and assessment frequency. Filter by commodity name (Crude Oil, Natural Gas, LNG, etc.).
  hints:
    openWorld: false
    readOnly: true
  name: list-commodity-symbols
- description: Get list of commodity symbols with updated price assessments since a given date. Use for incremental data sync to keep commodity price databases current.
  hints:
    openWorld: false
    readOnly: true
  name: get-modified-commodity-symbols
---
