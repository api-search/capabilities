---
api_specs:
- filename: bls-public-data-api-openapi.yml
  format: yaml
  label: bls-public-data
  slug: bls-public-data
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/us-bureau-of-labor-statistics/refs/heads/main/openapi/bls-public-data-api-openapi.yml
categories: []
consumed_apis:
- bls-public-data
description: Unified capability for accessing Bureau of Labor Statistics time series data, including employment, unemployment, inflation (CPI), wages, and occupational statistics. Designed for economic researchers, HR analysts, policy teams, and data journalists who need programmatic access to authoritative US labor data.
layout: capability
name: BLS Labor Statistics Data Access
operations:
- description: Retrieve time series data for one or more BLS series IDs
  method: POST
  name: query-time-series
  path: /v1/time-series
- description: Retrieve historical data for a specific BLS series
  method: GET
  name: get-series-data
  path: /v1/time-series/{seriesId}
- description: List all BLS survey programs and abbreviations
  method: GET
  name: list-surveys
  path: /v1/surveys
- description: Get metadata for a specific BLS survey
  method: GET
  name: get-survey
  path: /v1/surveys/{surveyAbbreviation}
- description: Get the 25 most popular BLS series identifiers
  method: GET
  name: get-popular-series
  path: /v1/popular-series
personas: []
provider_name: US Bureau of Labor Statistics
provider_slug: us-bureau-of-labor-statistics
search_terms:
- open data
- retrieve historical data for a specific bls series
- federal government
- survey metadata
- list all bls survey programs and abbreviations
- get metadata for a specific bls survey
- get detailed metadata for a specific bls survey program
- query bls statistical time series data
- get the 25 most popular bls series identifiers
- labor statistics
- economic data
- list surveys
- query bls time series data for employment, unemployment, cpi, wages, or any other bls statistical series by series id and date range
- unemployment
- wages
- get popular series
- employment
- retrieve historical data for a single bls series id (e.g., lns14000000 for unemployment rate, cuur0000sa0 for cpi)
- get time series data for a specific series
- consumer price index
- bls survey catalog
- most popular bls series
- retrieve time series data for one or more bls series ids
- get survey details
- get survey
- get series data
- query time series
- get the 25 most popular bls series ids, useful for discovering commonly referenced economic indicators like unemployment rate and cpi
- list all bls survey programs to discover available data types
slug: labor-statistics-data
source_filename: labor-statistics-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: BLS Labor Statistics Data Access\n  description: >-\n    Unified capability for accessing Bureau of Labor Statistics time series data,\n    including employment, unemployment, inflation (CPI), wages, and occupational\n    statistics. Designed for economic researchers, HR analysts, policy teams, and\n    data journalists who need programmatic access to authoritative US labor data.\n  tags:\n    - Federal Government\n    - Labor Statistics\n    - Economic Data\n    - Employment\n    - Unemployment\n    - Consumer Price Index\n    - Wages\n    - Open Data\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      BLS_REGISTRATION_KEY: BLS_REGISTRATION_KEY\n\ncapability:\n  consumes:\n    - import: bls-public-data\n      location: ./shared/bls-public-data-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: bls-labor-statistics-api\n      description: Unified REST API\
  \ for BLS labor statistics data access.\n      resources:\n        - path: /v1/time-series\n          name: time-series\n          description: Query BLS statistical time series data\n          operations:\n            - method: POST\n              name: query-time-series\n              description: Retrieve time series data for one or more BLS series IDs\n              call: \"bls-public-data.get-multiple-time-series\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/time-series/{seriesId}\n          name: time-series-item\n          description: Get time series data for a specific series\n          operations:\n            - method: GET\n              name: get-series-data\n              description: Retrieve historical data for a specific BLS series\n              call: \"bls-public-data.get-single-time-series\"\n              with:\n                seriesId: \"rest.seriesId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/surveys\n          name: surveys\n          description: BLS survey catalog\n          operations:\n            - method: GET\n              name: list-surveys\n              description: List all BLS survey programs and abbreviations\n              call: \"bls-public-data.list-surveys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/surveys/{surveyAbbreviation}\n          name: survey-detail\n          description: Survey metadata\n          operations:\n            - method: GET\n              name: get-survey\n              description: Get metadata for a specific BLS survey\n              call: \"bls-public-data.get-survey-details\"\n              with:\n                surveyAbbreviation: \"rest.surveyAbbreviation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n     \
  \   - path: /v1/popular-series\n          name: popular-series\n          description: Most popular BLS series\n          operations:\n            - method: GET\n              name: get-popular-series\n              description: Get the 25 most popular BLS series identifiers\n              call: \"bls-public-data.get-popular-series\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: bls-labor-statistics-mcp\n      transport: http\n      description: MCP server for AI-assisted access to BLS labor statistics data.\n      tools:\n        - name: query-time-series\n          description: >-\n            Query BLS time series data for employment, unemployment, CPI, wages,\n            or any other BLS statistical series by series ID and date range\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"bls-public-data.get-multiple-time-series\"\n   \
  \       outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-series-data\n          description: >-\n            Retrieve historical data for a single BLS series ID (e.g.,\n            LNS14000000 for unemployment rate, CUUR0000SA0 for CPI)\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"bls-public-data.get-single-time-series\"\n          with:\n            seriesId: \"tools.seriesId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-surveys\n          description: List all BLS survey programs to discover available data types\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bls-public-data.list-surveys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-survey-details\n          description: Get detailed metadata for a specific BLS survey\
  \ program\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bls-public-data.get-survey-details\"\n          with:\n            surveyAbbreviation: \"tools.surveyAbbreviation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-popular-series\n          description: >-\n            Get the 25 most popular BLS series IDs, useful for discovering\n            commonly referenced economic indicators like unemployment rate and CPI\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bls-public-data.get-popular-series\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-bureau-of-labor-statistics/refs/heads/main/capabilities/labor-statistics-data.yaml
tags:
- Federal Government
- Labor Statistics
- Economic Data
- Employment
- Unemployment
- Consumer Price Index
- Wages
- Open Data
tools:
- description: Query BLS time series data for employment, unemployment, CPI, wages, or any other BLS statistical series by series ID and date range
  hints:
    openWorld: true
    readOnly: true
  name: query-time-series
- description: Retrieve historical data for a single BLS series ID (e.g., LNS14000000 for unemployment rate, CUUR0000SA0 for CPI)
  hints:
    openWorld: true
    readOnly: true
  name: get-series-data
- description: List all BLS survey programs to discover available data types
  hints:
    openWorld: false
    readOnly: true
  name: list-surveys
- description: Get detailed metadata for a specific BLS survey program
  hints:
    openWorld: false
    readOnly: true
  name: get-survey-details
- description: Get the 25 most popular BLS series IDs, useful for discovering commonly referenced economic indicators like unemployment rate and CPI
  hints:
    openWorld: false
    readOnly: true
  name: get-popular-series
---
