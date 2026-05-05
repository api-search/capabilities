---
api_specs:
- filename: blpapi-core.yml
  format: yaml
  label: blpapi
  slug: blpapi
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/bloomberg/refs/heads/main/openapi/blpapi-core.yml
categories: []
consumed_apis:
- blpapi
description: Unified workflow for accessing Bloomberg reference data, historical data, intraday analytics, and field discovery. Used by quantitative analysts and portfolio managers.
layout: capability
name: Bloomberg Market Data
operations:
- description: Request reference data.
  method: POST
  name: reference-data-request
  path: /v1/reference-data
- description: Request historical data.
  method: POST
  name: historical-data-request
  path: /v1/historical-data
- description: Request intraday bars.
  method: POST
  name: intraday-bar-request
  path: /v1/intraday-bars
- description: Request intraday ticks.
  method: POST
  name: intraday-tick-request
  path: /v1/intraday-ticks
- description: Look up field metadata.
  method: POST
  name: field-info-request
  path: /v1/fields
- description: Search for fields.
  method: POST
  name: field-search-request
  path: /v1/fields
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- news
- subscribe market vwap
- intraday bar request
- subscribe to custom vwap stream.
- market data
- request intraday bars.
- request intraday ticks.
- reference data queries.
- bloomberg
- look up field metadata.
- subscribe to interval-based real-time bars.
- enterprise
- business intelligence
- intraday tick queries.
- analytics
- subscribe market data
- request reference data for securities and fields.
- subscribe to streaming real-time market data.
- request end-of-day historical data for securities.
- request intraday ohlc bars for a security.
- search the bloomberg api data dictionary for fields.
- subscribe market bar
- reference data request
- transaction cost analysis
- intraday tick request
- historical data request
- intraday bar queries.
- search for fields.
- data license
- execution management
- trading
- look up metadata for bloomberg field mnemonics.
- field discovery.
- field search request
- field info request
- request raw intraday tick data for a security.
- request historical data.
- historical data queries.
- financial services
- request reference data.
- quantitative analysis
slug: market-data
source_filename: market-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Bloomberg Market Data\"\n  description: \"Unified workflow for accessing Bloomberg reference data, historical data, intraday analytics, and field discovery. Used by quantitative analysts and portfolio managers.\"\n  tags:\n    - Bloomberg\n    - Market Data\n    - Financial Services\n    - Quantitative Analysis\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      BLOOMBERG_SESSION_TOKEN: BLOOMBERG_SESSION_TOKEN\n\ncapability:\n  consumes:\n    - import: blpapi\n      location: ./shared/blpapi-core.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: market-data-api\n      description: \"Unified REST API for Bloomberg market data access.\"\n      resources:\n        - path: /v1/reference-data\n          name: reference-data\n          description: \"Reference data queries.\"\n          operations:\n            - method: POST\n              name: reference-data-request\n\
  \              description: \"Request reference data.\"\n              call: \"blpapi.reference-data-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/historical-data\n          name: historical-data\n          description: \"Historical data queries.\"\n          operations:\n            - method: POST\n              name: historical-data-request\n              description: \"Request historical data.\"\n              call: \"blpapi.historical-data-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/intraday-bars\n          name: intraday-bars\n          description: \"Intraday bar queries.\"\n          operations:\n            - method: POST\n              name: intraday-bar-request\n              description: \"Request intraday bars.\"\n              call: \"blpapi.intraday-bar-request\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n        - path: /v1/intraday-ticks\n          name: intraday-ticks\n          description: \"Intraday tick queries.\"\n          operations:\n            - method: POST\n              name: intraday-tick-request\n              description: \"Request intraday ticks.\"\n              call: \"blpapi.intraday-tick-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/fields\n          name: fields\n          description: \"Field discovery.\"\n          operations:\n            - method: POST\n              name: field-info-request\n              description: \"Look up field metadata.\"\n              call: \"blpapi.field-info-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: field-search-request\n              description: \"Search for fields.\"\
  \n              call: \"blpapi.field-search-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: market-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Bloomberg market data analysis.\"\n      tools:\n        - name: reference-data-request\n          description: \"Request reference data for securities and fields.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"blpapi.reference-data-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: historical-data-request\n          description: \"Request end-of-day historical data for securities.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"blpapi.historical-data-request\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: intraday-bar-request\n          description: \"Request intraday OHLC bars for a security.\"\n          hints:\n            readOnly: true\n          call: \"blpapi.intraday-bar-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: intraday-tick-request\n          description: \"Request raw intraday tick data for a security.\"\n          hints:\n            readOnly: true\n          call: \"blpapi.intraday-tick-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: field-info-request\n          description: \"Look up metadata for Bloomberg field mnemonics.\"\n          hints:\n            readOnly: true\n          call: \"blpapi.field-info-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: field-search-request\n          description: \"Search the Bloomberg API Data Dictionary for\
  \ fields.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"blpapi.field-search-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: subscribe-market-data\n          description: \"Subscribe to streaming real-time market data.\"\n          hints:\n            readOnly: true\n          call: \"blpapi.subscribe-market-data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: subscribe-market-bar\n          description: \"Subscribe to interval-based real-time bars.\"\n          hints:\n            readOnly: true\n          call: \"blpapi.subscribe-market-bar\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: subscribe-market-vwap\n          description: \"Subscribe to custom VWAP stream.\"\n          hints:\n            readOnly: true\n          call: \"blpapi.subscribe-market-vwap\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bloomberg/refs/heads/main/capabilities/market-data.yaml
tags:
- Bloomberg
- Market Data
- Financial Services
- Quantitative Analysis
tools:
- description: Request reference data for securities and fields.
  hints:
    openWorld: true
    readOnly: true
  name: reference-data-request
- description: Request end-of-day historical data for securities.
  hints:
    openWorld: true
    readOnly: true
  name: historical-data-request
- description: Request intraday OHLC bars for a security.
  hints:
    readOnly: true
  name: intraday-bar-request
- description: Request raw intraday tick data for a security.
  hints:
    readOnly: true
  name: intraday-tick-request
- description: Look up metadata for Bloomberg field mnemonics.
  hints:
    readOnly: true
  name: field-info-request
- description: Search the Bloomberg API Data Dictionary for fields.
  hints:
    openWorld: true
    readOnly: true
  name: field-search-request
- description: Subscribe to streaming real-time market data.
  hints:
    readOnly: true
  name: subscribe-market-data
- description: Subscribe to interval-based real-time bars.
  hints:
    readOnly: true
  name: subscribe-market-bar
- description: Subscribe to custom VWAP stream.
  hints:
    readOnly: true
  name: subscribe-market-vwap
---
