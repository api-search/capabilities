---
categories: []
consumed_apis:
- data-license
- http-api
description: Workflow for accessing Bloomberg market data combining the Data License HAPI for bulk data with the HTTP API for real-time reference and historical data, used by quantitative analysts and portfolio managers.
layout: capability
name: Bloomberg Market Data and Analytics
operations:
- description: List available data catalogs
  method: GET
  name: list-catalogs
  path: /v1/catalogs
- description: List security universes
  method: GET
  name: list-universes
  path: /v1/universes
- description: List field lists
  method: GET
  name: list-field-lists
  path: /v1/field-lists
- description: Get reference data for securities
  method: POST
  name: get-reference-data
  path: /v1/reference-data
- description: Get historical end-of-day data
  method: POST
  name: get-historical-data
  path: /v1/historical-data
- description: List completed data distributions
  method: GET
  name: list-distributions
  path: /v1/distributions
personas: []
provider_name: Bloomberg AIM
provider_slug: bloomberg-aim
search_terms:
- list available data catalogs
- get intraday bars
- get reference data for securities via http api
- search fields
- create a bloomberg data request
- search for securities and instruments
- reference data access
- search instruments
- trading
- market data
- get reference data for securities
- list universes
- get historical end-of-day data
- list available bloomberg data catalogs
- get data catalog details
- get intraday bar data
- list completed data distributions
- get reference data
- list distributions
- data distributions
- list catalogs
- create universe
- get historical data
- get historical data for securities
- data catalog browsing
- security universe management
- list field lists
- field list management
- portfolio management
- list security universes
- historical data access
- financial data
- create data request
- order management
- list field lists for data requests
- reference data
- financial analytics
- get catalog
- create a security universe for data requests
- search available bloomberg data fields
- bloomberg
slug: market-data-and-analytics
source_filename: market-data-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Bloomberg Market Data and Analytics\"\n  description: \"Workflow for accessing Bloomberg market data combining the Data License HAPI for bulk data with the HTTP API for real-time reference and historical data, used by quantitative analysts and portfolio managers.\"\n  tags:\n    - Bloomberg\n    - Market Data\n    - Financial Analytics\n    - Reference Data\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      BLOOMBERG_HAPI_TOKEN: BLOOMBERG_HAPI_TOKEN\n      BLOOMBERG_HTTP_USERNAME: BLOOMBERG_HTTP_USERNAME\n      BLOOMBERG_HTTP_PASSWORD: BLOOMBERG_HTTP_PASSWORD\n\ncapability:\n  consumes:\n    - import: data-license\n      location: ./shared/data-license.yaml\n    - import: http-api\n      location: ./shared/http-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: market-data-api\n      description: \"Unified REST API for Bloomberg market data and analytics.\"\
  \n      resources:\n        - path: /v1/catalogs\n          name: catalogs\n          description: \"Data catalog browsing\"\n          operations:\n            - method: GET\n              name: list-catalogs\n              description: \"List available data catalogs\"\n              call: \"data-license.list-catalogs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/universes\n          name: universes\n          description: \"Security universe management\"\n          operations:\n            - method: GET\n              name: list-universes\n              description: \"List security universes\"\n              call: \"data-license.list-universes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/field-lists\n          name: field-lists\n          description: \"Field list management\"\n          operations:\n            - method: GET\n   \
  \           name: list-field-lists\n              description: \"List field lists\"\n              call: \"data-license.list-field-lists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reference-data\n          name: reference-data\n          description: \"Reference data access\"\n          operations:\n            - method: POST\n              name: get-reference-data\n              description: \"Get reference data for securities\"\n              call: \"http-api.get-reference-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/historical-data\n          name: historical-data\n          description: \"Historical data access\"\n          operations:\n            - method: POST\n              name: get-historical-data\n              description: \"Get historical end-of-day data\"\n              call: \"http-api.get-historical-data\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/distributions\n          name: distributions\n          description: \"Data distributions\"\n          operations:\n            - method: GET\n              name: list-distributions\n              description: \"List completed data distributions\"\n              call: \"data-license.list-distributions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: market-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Bloomberg market data access.\"\n      tools:\n        - name: list-catalogs\n          description: \"List available Bloomberg data catalogs\"\n          hints:\n            readOnly: true\n          call: \"data-license.list-catalogs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n    \
  \    - name: get-catalog\n          description: \"Get data catalog details\"\n          hints:\n            readOnly: true\n          call: \"data-license.get-catalog\"\n          with:\n            catalogId: \"tools.catalogId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-universes\n          description: \"List security universes\"\n          hints:\n            readOnly: true\n          call: \"data-license.list-universes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-universe\n          description: \"Create a security universe for data requests\"\n          hints:\n            readOnly: false\n          call: \"data-license.create-universe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-field-lists\n          description: \"List field lists for data requests\"\n          hints:\n      \
  \      readOnly: true\n          call: \"data-license.list-field-lists\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-data-request\n          description: \"Create a Bloomberg data request\"\n          hints:\n            readOnly: false\n          call: \"data-license.create-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-distributions\n          description: \"List completed data distributions\"\n          hints:\n            readOnly: true\n          call: \"data-license.list-distributions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-reference-data\n          description: \"Get reference data for securities via HTTP API\"\n          hints:\n            readOnly: true\n          call: \"http-api.get-reference-data\"\n          outputParameters:\n            - type: object\n        \
  \      mapping: \"$.\"\n        - name: get-historical-data\n          description: \"Get historical data for securities\"\n          hints:\n            readOnly: true\n          call: \"http-api.get-historical-data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-intraday-bars\n          description: \"Get intraday bar data\"\n          hints:\n            readOnly: true\n          call: \"http-api.get-intraday-bars\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-fields\n          description: \"Search available Bloomberg data fields\"\n          hints:\n            readOnly: true\n          call: \"http-api.search-fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-instruments\n          description: \"Search for securities and instruments\"\n          hints:\n            readOnly: true\n\
  \          call: \"http-api.search-instruments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bloomberg-aim/refs/heads/main/capabilities/market-data-and-analytics.yaml
tags:
- Bloomberg
- Market Data
- Financial Analytics
- Reference Data
tools:
- description: List available Bloomberg data catalogs
  hints:
    readOnly: true
  name: list-catalogs
- description: Get data catalog details
  hints:
    readOnly: true
  name: get-catalog
- description: List security universes
  hints:
    readOnly: true
  name: list-universes
- description: Create a security universe for data requests
  hints:
    readOnly: false
  name: create-universe
- description: List field lists for data requests
  hints:
    readOnly: true
  name: list-field-lists
- description: Create a Bloomberg data request
  hints:
    readOnly: false
  name: create-data-request
- description: List completed data distributions
  hints:
    readOnly: true
  name: list-distributions
- description: Get reference data for securities via HTTP API
  hints:
    readOnly: true
  name: get-reference-data
- description: Get historical data for securities
  hints:
    readOnly: true
  name: get-historical-data
- description: Get intraday bar data
  hints:
    readOnly: true
  name: get-intraday-bars
- description: Search available Bloomberg data fields
  hints:
    readOnly: true
  name: search-fields
- description: Search for securities and instruments
  hints:
    readOnly: true
  name: search-instruments
---
