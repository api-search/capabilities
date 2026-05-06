---
categories: []
consumed_apis: []
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
- data catalog browsing
- list field lists
- get intraday bar data
- search instruments
- market data
- reference data access
- reference data
- historical data access
- list security universes
- data distributions
- list field lists for data requests
- create a bloomberg data request
- list catalogs
- get catalog
- portfolio management
- list available bloomberg data catalogs
- get reference data
- create data request
- security universe management
- get reference data for securities
- bloomberg
- list universes
- trading
- search fields
- get data catalog details
- financial data
- financial analytics
- create universe
- get historical end-of-day data
- list distributions
- get reference data for securities via http api
- list available data catalogs
- field list management
- get intraday bars
- list completed data distributions
- order management
- get historical data for securities
- search for securities and instruments
- get historical data
- search available bloomberg data fields
- create a security universe for data requests
slug: market-data-and-analytics
source_filename: market-data-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bloomberg Market Data and Analytics\n  description: Workflow for accessing Bloomberg market data combining the Data License HAPI for bulk data with the HTTP API\n    for real-time reference and historical data, used by quantitative analysts and portfolio managers.\n  tags:\n  - Bloomberg\n  - Market Data\n  - Financial Analytics\n  - Reference Data\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BLOOMBERG_HAPI_TOKEN: BLOOMBERG_HAPI_TOKEN\n    BLOOMBERG_HTTP_USERNAME: BLOOMBERG_HTTP_USERNAME\n    BLOOMBERG_HTTP_PASSWORD: BLOOMBERG_HTTP_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: data-license\n    baseUri: https://api.bloomberg.com/eap\n    description: Bloomberg Data License HAPI for financial data\n    authentication:\n      type: bearer\n      token: '{{BLOOMBERG_HAPI_TOKEN}}'\n    resources:\n    - name: catalogs\n      path: /catalogs\n      description: Data catalog\
  \ browsing\n      operations:\n      - name: list-catalogs\n        method: GET\n        description: List available data catalogs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-catalog\n        method: GET\n        description: Get catalog details\n        inputParameters:\n        - name: catalogId\n          in: path\n          type: string\n          required: true\n          description: Catalog identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: universes\n      path: /universes\n      description: Security universe management\n      operations:\n      - name: list-universes\n        method: GET\n        description: List security universes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-universe\n\
  \        method: POST\n        description: Create a security universe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            identifier: '{{tools.identifier}}'\n            title: '{{tools.title}}'\n      - name: get-universe\n        method: GET\n        description: Get universe details\n        inputParameters:\n        - name: universeId\n          in: path\n          type: string\n          required: true\n          description: Universe identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-universe\n        method: DELETE\n        description: Delete a universe\n        inputParameters:\n        - name: universeId\n          in: path\n          type: string\n          required: true\n          description: Universe identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: field-lists\n      path: /fieldLists\n      description: Field list management\n      operations:\n      - name: list-field-lists\n        method: GET\n        description: List field lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-field-list\n        method: POST\n        description: Create a field list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-field-list\n        method: GET\n        description: Get field list details\n        inputParameters:\n        - name: fieldListId\n          in: path\n          type: string\n          required: true\n          description: Field list identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: requests\n      path: /requests\n      description: Data request management\n      operations:\n      - name: list-requests\n        method: GET\n        description: List data requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-request\n        method: POST\n        description: Create a data request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: distributions\n      path: /distributions\n      description: Data distribution access\n      operations:\n      - name: list-distributions\n        method: GET\n        description: List data distributions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-distribution\n        method: GET\n    \
  \    description: Get distribution details and download URL\n        inputParameters:\n        - name: distributionId\n          in: path\n          type: string\n          required: true\n          description: Distribution identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: http-api\n    baseUri: https://localhost:3000\n    description: Bloomberg HTTP API for reference and historical data\n    authentication:\n      type: basic\n      username: '{{BLOOMBERG_HTTP_USERNAME}}'\n      password: '{{BLOOMBERG_HTTP_PASSWORD}}'\n    resources:\n    - name: request\n      path: /request\n      description: Generic BLPAPI request endpoint\n      operations:\n      - name: send-request\n        method: POST\n        description: Send a BLPAPI request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \       body:\n          type: json\n          data:\n            service: '{{tools.service}}'\n            operation: '{{tools.operation}}'\n            parameters: '{{tools.parameters}}'\n    - name: reference-data\n      path: /request\n      description: Reference data requests\n      operations:\n      - name: get-reference-data\n        method: POST\n        description: Get reference data for securities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            service: //blp/refdata\n            operation: ReferenceDataRequest\n            parameters:\n              securities: '{{tools.securities}}'\n              fields: '{{tools.fields}}'\n    - name: historical-data\n      path: /request\n      description: Historical data requests\n      operations:\n      - name: get-historical-data\n        method: POST\n        description: Get historical\
  \ end-of-day data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            service: //blp/refdata\n            operation: HistoricalDataRequest\n            parameters:\n              securities: '{{tools.securities}}'\n              fields: '{{tools.fields}}'\n              startDate: '{{tools.startDate}}'\n              endDate: '{{tools.endDate}}'\n    - name: intraday-data\n      path: /request\n      description: Intraday data requests\n      operations:\n      - name: get-intraday-bars\n        method: POST\n        description: Get intraday bar data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-intraday-ticks\n        method: POST\n        description: Get intraday tick data\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: field-search\n      path: /request\n      description: Field discovery\n      operations:\n      - name: search-fields\n        method: POST\n        description: Search available data fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-field-info\n        method: POST\n        description: Get field metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instruments\n      path: /request\n      description: Instrument search\n      operations:\n      - name: search-instruments\n        method: POST\n        description: Search for securities and instruments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n \
  \   namespace: market-data-api\n    description: Unified REST API for Bloomberg market data and analytics.\n    resources:\n    - path: /v1/catalogs\n      name: catalogs\n      description: Data catalog browsing\n      operations:\n      - method: GET\n        name: list-catalogs\n        description: List available data catalogs\n        call: data-license.list-catalogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/universes\n      name: universes\n      description: Security universe management\n      operations:\n      - method: GET\n        name: list-universes\n        description: List security universes\n        call: data-license.list-universes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/field-lists\n      name: field-lists\n      description: Field list management\n      operations:\n      - method: GET\n        name: list-field-lists\n        description: List field lists\n        call:\
  \ data-license.list-field-lists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reference-data\n      name: reference-data\n      description: Reference data access\n      operations:\n      - method: POST\n        name: get-reference-data\n        description: Get reference data for securities\n        call: http-api.get-reference-data\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/historical-data\n      name: historical-data\n      description: Historical data access\n      operations:\n      - method: POST\n        name: get-historical-data\n        description: Get historical end-of-day data\n        call: http-api.get-historical-data\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/distributions\n      name: distributions\n      description: Data distributions\n      operations:\n      - method: GET\n        name: list-distributions\n        description:\
  \ List completed data distributions\n        call: data-license.list-distributions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: market-data-mcp\n    transport: http\n    description: MCP server for AI-assisted Bloomberg market data access.\n    tools:\n    - name: list-catalogs\n      description: List available Bloomberg data catalogs\n      hints:\n        readOnly: true\n      call: data-license.list-catalogs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-catalog\n      description: Get data catalog details\n      hints:\n        readOnly: true\n      call: data-license.get-catalog\n      with:\n        catalogId: tools.catalogId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-universes\n      description: List security universes\n      hints:\n        readOnly: true\n      call: data-license.list-universes\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-universe\n      description: Create a security universe for data requests\n      hints:\n        readOnly: false\n      call: data-license.create-universe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-field-lists\n      description: List field lists for data requests\n      hints:\n        readOnly: true\n      call: data-license.list-field-lists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-data-request\n      description: Create a Bloomberg data request\n      hints:\n        readOnly: false\n      call: data-license.create-request\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-distributions\n      description: List completed data distributions\n      hints:\n        readOnly: true\n      call: data-license.list-distributions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-reference-data\n      description: Get reference data for securities via HTTP API\n      hints:\n        readOnly: true\n      call: http-api.get-reference-data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-historical-data\n      description: Get historical data for securities\n      hints:\n        readOnly: true\n      call: http-api.get-historical-data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-intraday-bars\n      description: Get intraday bar data\n      hints:\n        readOnly: true\n      call: http-api.get-intraday-bars\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-fields\n      description: Search available Bloomberg data fields\n      hints:\n        readOnly: true\n      call: http-api.search-fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-instruments\n      description: Search for securities and instruments\n\
  \      hints:\n        readOnly: true\n      call: http-api.search-instruments\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
