---
categories: []
consumed_apis:
- redfin-stingray
- redfin-data-center
description: Unified capability for housing market analytics and data access on Redfin. Combines regional market trend data from the Stingray API and bulk market tracker datasets from the Data Center. Supports analysts, data scientists, and market researchers tracking housing trends at all geographic levels from national to neighborhood.
layout: capability
name: Redfin Market Analytics
operations:
- description: Get market trend data for a region including prices, volume, and days on market.
  method: GET
  name: get-region-trends
  path: /v1/trends/{regionType}/{regionId}/{code}
- description: Download national housing market tracker dataset (compressed TSV).
  method: GET
  name: get-national-market-data
  path: /v1/market-data/national
- description: Download metro MSA housing market tracker dataset (compressed TSV).
  method: GET
  name: get-metro-market-data
  path: /v1/market-data/metro
- description: Download state-level housing market tracker dataset (compressed TSV).
  method: GET
  name: get-state-market-data
  path: /v1/market-data/state
- description: Download county-level housing market tracker dataset (compressed TSV).
  method: GET
  name: get-county-market-data
  path: /v1/market-data/county
- description: Download city-level housing market tracker dataset (compressed TSV).
  method: GET
  name: get-city-market-data
  path: /v1/market-data/city
- description: Download ZIP code housing market tracker dataset (compressed TSV).
  method: GET
  name: get-zip-code-market-data
  path: /v1/market-data/zip-code
- description: Download neighborhood housing market tracker dataset (compressed TSV).
  method: GET
  name: get-neighborhood-market-data
  path: /v1/market-data/neighborhood
personas: []
provider_name: Redfin
provider_slug: redfin
search_terms:
- property data
- download redfin city-level housing market tracker dataset.
- download metro msa housing market tracker dataset (compressed tsv).
- download city-level housing market tracker dataset (compressed tsv).
- housing market
- download redfin metro msa housing market tracker dataset.
- download neighborhood housing market tracker dataset (compressed tsv).
- home values
- csv export
- download county-level housing market tracker dataset (compressed tsv).
- real estate
- get market trend data for a region including prices, volume, and days on market.
- market analytics
- download redfin neighborhood-level housing market tracker dataset.
- get city market data
- get zip code market data
- get state market data
- national housing market tracker download.
- download national housing market tracker dataset (compressed tsv).
- data science
- download redfin state-level housing market tracker dataset.
- get county market data
- get national market data
- download redfin zip code housing market tracker dataset (most granular).
- download redfin national housing market tracker dataset with all key metrics.
- 'get housing market trends for a specific region: prices, volume, days on market, inventory.'
- download state-level housing market tracker dataset (compressed tsv).
- metro-level housing market tracker download.
- state-level housing market tracker download.
- regional market trends from stingray api.
- statistics
- download zip code housing market tracker dataset (compressed tsv).
- county-level housing market tracker download.
- zip code-level housing market tracker download.
- gis
- city-level housing market tracker download.
- neighborhood-level housing market tracker download.
- redfin
- get metro market data
- get neighborhood market data
- listings
- get region trends
slug: market-analytics
source_filename: market-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Redfin Market Analytics\"\n  description: >-\n    Unified capability for housing market analytics and data access on Redfin.\n    Combines regional market trend data from the Stingray API and bulk\n    market tracker datasets from the Data Center. Supports analysts, data\n    scientists, and market researchers tracking housing trends at all geographic\n    levels from national to neighborhood.\n  tags:\n    - Redfin\n    - Housing Market\n    - Market Analytics\n    - Real Estate\n    - Statistics\n    - Data Science\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\ncapability:\n  consumes:\n    - import: redfin-stingray\n      location: ./shared/stingray-api.yaml\n    - import: redfin-data-center\n      location: ./shared/data-center.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: redfin-market-analytics-api\n      description: \"Unified REST API for Redfin housing market analytics and data downloads.\"\
  \n      resources:\n        - path: /v1/trends/{regionType}/{regionId}/{code}\n          name: regional-trends\n          description: \"Regional market trends from Stingray API.\"\n          operations:\n            - method: GET\n              name: get-region-trends\n              description: \"Get market trend data for a region including prices, volume, and days on market.\"\n              call: \"redfin-stingray.get-region-trends\"\n              with:\n                regionType: \"rest.regionType\"\n                regionId: \"rest.regionId\"\n                code: \"rest.code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/market-data/national\n          name: national-market-data\n          description: \"National housing market tracker download.\"\n          operations:\n            - method: GET\n              name: get-national-market-data\n              description: \"Download national housing market\
  \ tracker dataset (compressed TSV).\"\n              call: \"redfin-data-center.download-national-market-tracker\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/market-data/metro\n          name: metro-market-data\n          description: \"Metro-level housing market tracker download.\"\n          operations:\n            - method: GET\n              name: get-metro-market-data\n              description: \"Download metro MSA housing market tracker dataset (compressed TSV).\"\n              call: \"redfin-data-center.download-metro-market-tracker\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/market-data/state\n          name: state-market-data\n          description: \"State-level housing market tracker download.\"\n          operations:\n            - method: GET\n              name: get-state-market-data\n              description:\
  \ \"Download state-level housing market tracker dataset (compressed TSV).\"\n              call: \"redfin-data-center.download-state-market-tracker\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/market-data/county\n          name: county-market-data\n          description: \"County-level housing market tracker download.\"\n          operations:\n            - method: GET\n              name: get-county-market-data\n              description: \"Download county-level housing market tracker dataset (compressed TSV).\"\n              call: \"redfin-data-center.download-county-market-tracker\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/market-data/city\n          name: city-market-data\n          description: \"City-level housing market tracker download.\"\n          operations:\n            - method: GET\n              name: get-city-market-data\n\
  \              description: \"Download city-level housing market tracker dataset (compressed TSV).\"\n              call: \"redfin-data-center.download-city-market-tracker\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/market-data/zip-code\n          name: zip-code-market-data\n          description: \"ZIP code-level housing market tracker download.\"\n          operations:\n            - method: GET\n              name: get-zip-code-market-data\n              description: \"Download ZIP code housing market tracker dataset (compressed TSV).\"\n              call: \"redfin-data-center.download-zip-code-market-tracker\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/market-data/neighborhood\n          name: neighborhood-market-data\n          description: \"Neighborhood-level housing market tracker download.\"\n          operations:\n \
  \           - method: GET\n              name: get-neighborhood-market-data\n              description: \"Download neighborhood housing market tracker dataset (compressed TSV).\"\n              call: \"redfin-data-center.download-neighborhood-market-tracker\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: redfin-market-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Redfin housing market analytics.\"\n      tools:\n        - name: get-region-trends\n          description: \"Get housing market trends for a specific region: prices, volume, days on market, inventory.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"redfin-stingray.get-region-trends\"\n          with:\n            regionType: \"tools.regionType\"\n            regionId: \"tools.regionId\"\n            code: \"tools.code\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-national-market-data\n          description: \"Download Redfin national housing market tracker dataset with all key metrics.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"redfin-data-center.download-national-market-tracker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-metro-market-data\n          description: \"Download Redfin metro MSA housing market tracker dataset.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"redfin-data-center.download-metro-market-tracker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-state-market-data\n          description: \"Download Redfin state-level housing market tracker dataset.\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"redfin-data-center.download-state-market-tracker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-city-market-data\n          description: \"Download Redfin city-level housing market tracker dataset.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"redfin-data-center.download-city-market-tracker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-zip-code-market-data\n          description: \"Download Redfin ZIP code housing market tracker dataset (most granular).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"redfin-data-center.download-zip-code-market-tracker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-neighborhood-market-data\n          description: \"Download Redfin neighborhood-level\
  \ housing market tracker dataset.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"redfin-data-center.download-neighborhood-market-tracker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/redfin/refs/heads/main/capabilities/market-analytics.yaml
tags:
- Redfin
- Housing Market
- Market Analytics
- Real Estate
- Statistics
- Data Science
tools:
- description: 'Get housing market trends for a specific region: prices, volume, days on market, inventory.'
  hints:
    openWorld: true
    readOnly: true
  name: get-region-trends
- description: Download Redfin national housing market tracker dataset with all key metrics.
  hints:
    openWorld: false
    readOnly: true
  name: get-national-market-data
- description: Download Redfin metro MSA housing market tracker dataset.
  hints:
    openWorld: false
    readOnly: true
  name: get-metro-market-data
- description: Download Redfin state-level housing market tracker dataset.
  hints:
    openWorld: false
    readOnly: true
  name: get-state-market-data
- description: Download Redfin city-level housing market tracker dataset.
  hints:
    openWorld: false
    readOnly: true
  name: get-city-market-data
- description: Download Redfin ZIP code housing market tracker dataset (most granular).
  hints:
    openWorld: false
    readOnly: true
  name: get-zip-code-market-data
- description: Download Redfin neighborhood-level housing market tracker dataset.
  hints:
    openWorld: false
    readOnly: true
  name: get-neighborhood-market-data
---
