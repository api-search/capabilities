---
categories: []
consumed_apis:
- spg-commodity-insights
- kensho-link
description: Unified financial data analytics workflow combining S&P Global Commodity Insights market data with Kensho entity resolution. Used by financial analysts, quant teams, energy traders, and data scientists to integrate commodity pricing with entity identification across S&P Global data assets.
layout: capability
name: S&P Global Financial Data Analytics
operations:
- description: Get current price assessments for specified commodity symbols
  method: GET
  name: get-current-prices
  path: /v1/prices/current
- description: Get historical price assessments over a date range
  method: GET
  name: get-price-history
  path: /v1/prices/history
- description: List available commodity symbols
  method: GET
  name: list-symbols
  path: /v1/symbols
- description: Resolve entity mentions to canonical KEIDs
  method: POST
  name: link-entity
  path: /v1/entities/link
- description: Get entity record by KEID with cross-references
  method: GET
  name: get-entity
  path: /v1/entities/{keid}
- description: Search for financial entities
  method: GET
  name: search-entities
  path: /v1/entities/search
personas: []
provider_name: S&P Global
provider_slug: s-and-p-global
search_terms:
- get historical commodity price assessments for a date range. use for time series analysis, backtesting, and trend analysis in energy and commodity markets.
- link entity
- list available commodity symbols
- get current commodity prices
- entity resolution
- get the latest price assessments for platts commodity symbols (e.g., pcaas00 for dated brent crude oil). returns current value, unit of measure, currency, and assessment date.
- resolve entity mentions to canonical keids
- resolve a financial entity mention (company name, ticker, cusip, isin) to its canonical kensho entity identifier (keid) with confidence scores and cross-references.
- get entity by keid
- commodity symbol reference data
- get historical price assessments over a date range
- credit ratings
- historical commodity price assessments
- get entity record by keid with cross-references
- list commodity symbols
- capital markets
- get the full canonical entity record for a keid including aliases, cross-references (ticker, cusip, isin, lei, s&p global company id).
- market data
- fortune 500
- search for financial entities
- get list of commodity symbols with updated price assessments since a given date. use for incremental data sync.
- energy markets
- get entity
- search financial entities
- get modified commodity symbols
- link financial entity
- trading
- list available platts commodity symbols with descriptions, units, and assessment frequency. filter by commodity name (crude oil, natural gas, lng, etc.).
- market intelligence
- analytics
- get price history
- financial data
- commodity insights
- canonical entity record
- get current prices
- current commodity price assessments
- search entities
- get historical commodity prices
- entity resolution and linking
- s&p global
- get current price assessments for specified commodity symbols
- search for financial entities (companies, instruments, funds, indices) by name or identifier. returns ranked candidates with confidence scores.
- entity search by name or identifier
- list symbols
slug: financial-data-analytics
source_filename: financial-data-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"S&P Global Financial Data Analytics\"\n  description: \"Unified financial data analytics workflow combining S&P Global Commodity Insights market data with Kensho entity resolution. Used by financial analysts, quant teams, energy traders, and data scientists to integrate commodity pricing with entity identification across S&P Global data assets.\"\n  tags:\n    - S&P Global\n    - Financial Data\n    - Commodity Insights\n    - Entity Resolution\n    - Market Data\n    - Analytics\n    - Trading\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPG_CI_ACCESS_TOKEN: SPG_CI_ACCESS_TOKEN\n      KENSHO_LINK_TOKEN: KENSHO_LINK_TOKEN\n\ncapability:\n  consumes:\n    - import: spg-commodity-insights\n      location: ./shared/commodity-insights.yaml\n    - import: kensho-link\n      location: ./shared/kensho-link.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace:\
  \ financial-data-analytics-api\n      description: \"Unified REST API for S&P Global financial data analytics combining commodity market data and entity resolution.\"\n      resources:\n        - path: /v1/prices/current\n          name: current-prices\n          description: \"Current commodity price assessments\"\n          operations:\n            - method: GET\n              name: get-current-prices\n              description: \"Get current price assessments for specified commodity symbols\"\n              call: \"spg-commodity-insights.get-current-market-data\"\n              with:\n                symbol: \"rest.symbol\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/prices/history\n          name: price-history\n          description: \"Historical commodity price assessments\"\n          operations:\n            - method: GET\n              name: get-price-history\n              description: \"Get historical\
  \ price assessments over a date range\"\n              call: \"spg-commodity-insights.get-historical-market-data\"\n              with:\n                symbol: \"rest.symbol\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/symbols\n          name: symbols\n          description: \"Commodity symbol reference data\"\n          operations:\n            - method: GET\n              name: list-symbols\n              description: \"List available commodity symbols\"\n              call: \"spg-commodity-insights.list-symbols\"\n              with:\n                commodityName: \"rest.commodityName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entities/link\n          name: entity-link\n          description: \"Entity resolution and linking\"\n         \
  \ operations:\n            - method: POST\n              name: link-entity\n              description: \"Resolve entity mentions to canonical KEIDs\"\n              call: \"kensho-link.link-entity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entities/{keid}\n          name: entity\n          description: \"Canonical entity record\"\n          operations:\n            - method: GET\n              name: get-entity\n              description: \"Get entity record by KEID with cross-references\"\n              call: \"kensho-link.get-entity\"\n              with:\n                keid: \"rest.keid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entities/search\n          name: entity-search\n          description: \"Entity search by name or identifier\"\n          operations:\n            - method: GET\n              name: search-entities\n\
  \              description: \"Search for financial entities\"\n              call: \"kensho-link.search-entities\"\n              with:\n                q: \"rest.q\"\n                entityType: \"rest.entityType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: financial-data-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted financial data analysis combining commodity pricing and entity intelligence.\"\n      tools:\n        - name: get-current-commodity-prices\n          description: \"Get the latest price assessments for Platts commodity symbols (e.g., PCAAS00 for Dated Brent crude oil). Returns current value, unit of measure, currency, and assessment date.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spg-commodity-insights.get-current-market-data\"\n          with:\n            symbol: \"\
  tools.symbol\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-historical-commodity-prices\n          description: \"Get historical commodity price assessments for a date range. Use for time series analysis, backtesting, and trend analysis in energy and commodity markets.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spg-commodity-insights.get-historical-market-data\"\n          with:\n            symbol: \"tools.symbol\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-commodity-symbols\n          description: \"List available Platts commodity symbols with descriptions, units, and assessment frequency. Filter by commodity name (Crude Oil, Natural Gas, LNG, etc.).\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"spg-commodity-insights.list-symbols\"\n          with:\n            commodityName: \"tools.commodityName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-modified-commodity-symbols\n          description: \"Get list of commodity symbols with updated price assessments since a given date. Use for incremental data sync.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spg-commodity-insights.get-modified-symbols\"\n          with:\n            modifiedDate: \"tools.modifiedDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: link-financial-entity\n          description: \"Resolve a financial entity mention (company name, ticker, CUSIP, ISIN) to its canonical Kensho Entity Identifier (KEID) with confidence scores and cross-references.\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"kensho-link.link-entity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-entity-by-keid\n          description: \"Get the full canonical entity record for a KEID including aliases, cross-references (ticker, CUSIP, ISIN, LEI, S&P Global Company ID).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"kensho-link.get-entity\"\n          with:\n            keid: \"tools.keid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-financial-entities\n          description: \"Search for financial entities (companies, instruments, funds, indices) by name or identifier. Returns ranked candidates with confidence scores.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"kensho-link.search-entities\"\n          with:\n            q: \"tools.q\"\n            entityType:\
  \ \"tools.entityType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/s-and-p-global/refs/heads/main/capabilities/financial-data-analytics.yaml
tags:
- S&P Global
- Financial Data
- Commodity Insights
- Entity Resolution
- Market Data
- Analytics
- Trading
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
- description: Get list of commodity symbols with updated price assessments since a given date. Use for incremental data sync.
  hints:
    openWorld: false
    readOnly: true
  name: get-modified-commodity-symbols
- description: Resolve a financial entity mention (company name, ticker, CUSIP, ISIN) to its canonical Kensho Entity Identifier (KEID) with confidence scores and cross-references.
  hints:
    openWorld: false
    readOnly: true
  name: link-financial-entity
- description: Get the full canonical entity record for a KEID including aliases, cross-references (ticker, CUSIP, ISIN, LEI, S&P Global Company ID).
  hints:
    openWorld: false
    readOnly: true
  name: get-entity-by-keid
- description: Search for financial entities (companies, instruments, funds, indices) by name or identifier. Returns ranked candidates with confidence scores.
  hints:
    openWorld: false
    readOnly: true
  name: search-financial-entities
---
