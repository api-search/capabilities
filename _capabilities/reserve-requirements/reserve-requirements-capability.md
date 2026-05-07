---
categories: []
consumed_apis: []
description: The Federal Reserve Economic Data (FRED) API provided by the Federal Reserve Bank of St. Louis offers programmatic access to over 800,000 economic time series including reserve requirement data, monetary base measures, H.6 Money Stock Measures, and historical aggregate reserve data from the discontinued H.3 release. The API uses API key authentication and returns data in JSON, XML, or other formats.
layout: capability
name: FRED API - Federal Reserve Economic Data
operations:
- description: Get Economic Series
  method: GET
  name: getseries
  path: /series
- description: Get Series Observations
  method: GET
  name: getseriesobservations
  path: /series/observations
- description: Search Series
  method: GET
  name: searchseries
  path: /series/search
- description: Get Category
  method: GET
  name: getcategory
  path: /category
- description: Get Category Series
  method: GET
  name: getcategoryseries
  path: /category/series
- description: List Releases
  method: GET
  name: listreleases
  path: /releases
- description: Get Release
  method: GET
  name: getrelease
  path: /release
- description: Get Release Series
  method: GET
  name: getreleaseseries
  path: /release/series
personas: []
provider_name: Reserve Requirements
provider_slug: reserve-requirements
search_terms:
- searchseries
- get release
- search series
- regulation d
- api
- getcategory
- reserve
- list releases
- monetary policy
- get series observations
- getseriesobservations
- reserve requirements
- get category series
- federal reserve
- finance
- getreleaseseries
- get category
- get economic series
- getrelease
- getcategoryseries
- getseries
- banking regulation
- listreleases
- get release series
- requirements
slug: reserve-requirements-capability
source_filename: reserve-requirements-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FRED API - Federal Reserve Economic Data\n  description: The Federal Reserve Economic Data (FRED) API provided by the Federal Reserve Bank of St. Louis offers programmatic\n    access to over 800,000 economic time series including reserve requirement data, monetary base measures, H.6 Money Stock\n    Measures, and historical aggregate reserve data from the discontinued H.3 release. The API uses API key authentication\n    and returns data in JSON, XML, or other formats.\n  tags:\n  - Reserve\n  - Requirements\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: reserve-requirements\n    baseUri: https://api.stlouisfed.org/fred\n    description: FRED API - Federal Reserve Economic Data HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_key\n      value: '{{RESERVE_REQUIREMENTS_TOKEN}}'\n    resources:\n    - name: series\n      path: /series\n\
  \      operations:\n      - name: getseries\n        method: GET\n        description: Get Economic Series\n        inputParameters:\n        - name: series_id\n          in: query\n          type: string\n          required: true\n          description: The FRED series ID (e.g., RESBALNS, BOGMBASE).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: series-observations\n      path: /series/observations\n      operations:\n      - name: getseriesobservations\n        method: GET\n        description: Get Series Observations\n        inputParameters:\n        - name: series_id\n          in: query\n          type: string\n          required: true\n          description: The FRED series ID.\n        - name: observation_start\n          in: query\n          type: string\n          description: Start date for observations (YYYY-MM-DD).\n        - name: observation_end\n          in: query\n          type:\
  \ string\n          description: End date for observations (YYYY-MM-DD).\n        - name: sort_order\n          in: query\n          type: string\n          description: Sort order for observations.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of observations to return.\n        - name: offset\n          in: query\n          type: integer\n          description: Offset for pagination.\n        - name: units\n          in: query\n          type: string\n          description: Units transformation for the data.\n        - name: frequency\n          in: query\n          type: string\n          description: Frequency of the data.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: series-search\n      path: /series/search\n      operations:\n      - name: searchseries\n        method: GET\n        description: Search Series\n        inputParameters:\n\
  \        - name: search_text\n          in: query\n          type: string\n          required: true\n          description: Search keywords (e.g., \"reserve requirements\", \"monetary base\").\n        - name: search_type\n          in: query\n          type: string\n          description: Type of search to perform.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results.\n        - name: offset\n          in: query\n          type: integer\n          description: Offset for pagination.\n        - name: order_by\n          in: query\n          type: string\n          description: Field to order results by.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: category\n      path: /category\n      operations:\n      - name: getcategory\n        method: GET\n        description: Get Category\n        inputParameters:\n        - name: category_id\n\
  \          in: query\n          type: integer\n          required: true\n          description: The category ID (e.g., 32217 for Reserve Requirements).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: category-series\n      path: /category/series\n      operations:\n      - name: getcategoryseries\n        method: GET\n        description: Get Category Series\n        inputParameters:\n        - name: category_id\n          in: query\n          type: integer\n          required: true\n          description: The category ID.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results.\n        - name: offset\n          in: query\n          type: integer\n          description: Offset for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: releases\n\
  \      path: /releases\n      operations:\n      - name: listreleases\n        method: GET\n        description: List Releases\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results.\n        - name: offset\n          in: query\n          type: integer\n          description: Offset for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: release\n      path: /release\n      operations:\n      - name: getrelease\n        method: GET\n        description: Get Release\n        inputParameters:\n        - name: release_id\n          in: query\n          type: integer\n          required: true\n          description: The release ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: release-series\n      path: /release/series\n\
  \      operations:\n      - name: getreleaseseries\n        method: GET\n        description: Get Release Series\n        inputParameters:\n        - name: release_id\n          in: query\n          type: integer\n          required: true\n          description: The release ID.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: reserve-requirements-rest\n    description: REST adapter for FRED API - Federal Reserve Economic Data.\n    resources:\n    - path: /series\n      name: getseries\n      operations:\n      - method: GET\n        name: getseries\n        description: Get Economic Series\n        call: reserve-requirements.getseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /series/observations\n\
  \      name: getseriesobservations\n      operations:\n      - method: GET\n        name: getseriesobservations\n        description: Get Series Observations\n        call: reserve-requirements.getseriesobservations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /series/search\n      name: searchseries\n      operations:\n      - method: GET\n        name: searchseries\n        description: Search Series\n        call: reserve-requirements.searchseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /category\n      name: getcategory\n      operations:\n      - method: GET\n        name: getcategory\n        description: Get Category\n        call: reserve-requirements.getcategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /category/series\n      name: getcategoryseries\n      operations:\n      - method: GET\n        name: getcategoryseries\n        description: Get\
  \ Category Series\n        call: reserve-requirements.getcategoryseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /releases\n      name: listreleases\n      operations:\n      - method: GET\n        name: listreleases\n        description: List Releases\n        call: reserve-requirements.listreleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /release\n      name: getrelease\n      operations:\n      - method: GET\n        name: getrelease\n        description: Get Release\n        call: reserve-requirements.getrelease\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /release/series\n      name: getreleaseseries\n      operations:\n      - method: GET\n        name: getreleaseseries\n        description: Get Release Series\n        call: reserve-requirements.getreleaseseries\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9090\n    namespace: reserve-requirements-mcp\n    transport: http\n    description: MCP adapter for FRED API - Federal Reserve Economic Data for AI agent use.\n    tools:\n    - name: getseries\n      description: Get Economic Series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: reserve-requirements.getseries\n      with:\n        series_id: tools.series_id\n      inputParameters:\n      - name: series_id\n        type: string\n        description: The FRED series ID (e.g., RESBALNS, BOGMBASE).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getseriesobservations\n      description: Get Series Observations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: reserve-requirements.getseriesobservations\n      with:\n        series_id: tools.series_id\n        observation_start: tools.observation_start\n       \
  \ observation_end: tools.observation_end\n        sort_order: tools.sort_order\n        limit: tools.limit\n        offset: tools.offset\n        units: tools.units\n        frequency: tools.frequency\n      inputParameters:\n      - name: series_id\n        type: string\n        description: The FRED series ID.\n        required: true\n      - name: observation_start\n        type: string\n        description: Start date for observations (YYYY-MM-DD).\n      - name: observation_end\n        type: string\n        description: End date for observations (YYYY-MM-DD).\n      - name: sort_order\n        type: string\n        description: Sort order for observations.\n      - name: limit\n        type: integer\n        description: Maximum number of observations to return.\n      - name: offset\n        type: integer\n        description: Offset for pagination.\n      - name: units\n        type: string\n        description: Units transformation for the data.\n      - name: frequency\n    \
  \    type: string\n        description: Frequency of the data.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchseries\n      description: Search Series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: reserve-requirements.searchseries\n      with:\n        search_text: tools.search_text\n        search_type: tools.search_type\n        limit: tools.limit\n        offset: tools.offset\n        order_by: tools.order_by\n      inputParameters:\n      - name: search_text\n        type: string\n        description: Search keywords (e.g., \"reserve requirements\", \"monetary base\").\n        required: true\n      - name: search_type\n        type: string\n        description: Type of search to perform.\n      - name: limit\n        type: integer\n        description: Maximum number of results.\n      - name: offset\n        type: integer\n        description: Offset for pagination.\n      - name: order_by\n\
  \        type: string\n        description: Field to order results by.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategory\n      description: Get Category\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: reserve-requirements.getcategory\n      with:\n        category_id: tools.category_id\n      inputParameters:\n      - name: category_id\n        type: integer\n        description: The category ID (e.g., 32217 for Reserve Requirements).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategoryseries\n      description: Get Category Series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: reserve-requirements.getcategoryseries\n      with:\n        category_id: tools.category_id\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: category_id\n\
  \        type: integer\n        description: The category ID.\n        required: true\n      - name: limit\n        type: integer\n        description: Maximum number of results.\n      - name: offset\n        type: integer\n        description: Offset for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreleases\n      description: List Releases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: reserve-requirements.listreleases\n      with:\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: limit\n        type: integer\n        description: Maximum number of results.\n      - name: offset\n        type: integer\n        description: Offset for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrelease\n      description: Get Release\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: reserve-requirements.getrelease\n      with:\n        release_id: tools.release_id\n      inputParameters:\n      - name: release_id\n        type: integer\n        description: The release ID.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreleaseseries\n      description: Get Release Series\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: reserve-requirements.getreleaseseries\n      with:\n        release_id: tools.release_id\n        limit: tools.limit\n      inputParameters:\n      - name: release_id\n        type: integer\n        description: The release ID.\n        required: true\n      - name: limit\n        type: integer\n        description: Maximum number of results.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    RESERVE_REQUIREMENTS_TOKEN: RESERVE_REQUIREMENTS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/reserve-requirements/refs/heads/main/capabilities/reserve-requirements-capability.yaml
tags:
- Reserve
- Requirements
- API
tools:
- description: Get Economic Series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getseries
- description: Get Series Observations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getseriesobservations
- description: Search Series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchseries
- description: Get Category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategory
- description: Get Category Series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategoryseries
- description: List Releases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreleases
- description: Get Release
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrelease
- description: Get Release Series
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreleaseseries
---
