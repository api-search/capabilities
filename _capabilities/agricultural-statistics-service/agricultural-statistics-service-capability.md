---
categories: []
consumed_apis: []
description: The QuickStats API provides direct programmatic access to the statistical information contained in the NASS Quick Stats database, covering official published aggregate estimates related to U.S. agricultural production from NASS surveys and the Census of Agriculture. Supports filtering by commodity, location (state, county, zip), and time with comparison operators. Returns data in JSON, XML, or CSV format. An API key is required. Maximum 50,000 records per request.
layout: capability
name: USDA NASS QuickStats API
operations:
- description: USDA NASS Get Statistics
  method: GET
  name: getstatistics
  path: /api_GET
- description: USDA NASS Get Parameter Values
  method: GET
  name: getparamvalues
  path: /get_param_values
- description: USDA NASS Get Record Counts
  method: GET
  name: getcounts
  path: /get_counts
personas: []
provider_name: Agricultural Statistics Service
provider_slug: agricultural-statistics-service
search_terms:
- traders and market analysts tracking crop and livestock production data
- usda nass get parameter values
- getcounts
- api
- usda nass get statistics
- usda nass get record counts
- crop production, harvested area, and yield data
- service
- agriculture
- getparamvalues
- academics and policy researchers studying agricultural production trends and statistics
- geospatial
- livestock inventory, production, and price data
- developers integrating nass geospatial cropland and vegetation data into mapping applications
- cropland mapping, vegetation indices, and soil moisture
- statistics
- federal government
- agricultural
- open data
- getstatistics
slug: agricultural-statistics-service-capability
source_filename: agricultural-statistics-service-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USDA NASS QuickStats API\n  description: The QuickStats API provides direct programmatic access to the statistical information contained in the NASS\n    Quick Stats database, covering official published aggregate estimates related to U.S. agricultural production from NASS\n    surveys and the Census of Agriculture. Supports filtering by commodity, location (state, county, zip), and time with comparison\n    operators. Returns data in JSON, XML, or CSV format. An API key is required. Maximum 50,000 records per request.\n  tags:\n  - Agricultural\n  - Statistics\n  - Service\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: agricultural-statistics-service\n    baseUri: https://quickstats.nass.usda.gov/api\n    description: USDA NASS QuickStats API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{AGRICULTURAL_STATISTICS_SERVICE_TOKEN}}'\n\
  \    resources:\n    - name: api-get\n      path: /api_GET\n      operations:\n      - name: getstatistics\n        method: GET\n        description: USDA NASS Get Statistics\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: API key obtained by registering at the QuickStats API portal.\n        - name: commodity_desc\n          in: query\n          type: string\n          description: Commodity description (e.g., CORN, SOYBEANS, CATTLE).\n        - name: class_desc\n          in: query\n          type: string\n          description: Commodity class description.\n        - name: statisticcat_desc\n          in: query\n          type: string\n          description: Statistical category (e.g., AREA HARVESTED, PRODUCTION, PRICE RECEIVED).\n        - name: unit_desc\n          in: query\n          type: string\n          description: Unit of measurement (e.g., ACRES, BU, HEAD).\n        - name: sector_desc\n\
  \          in: query\n          type: string\n          description: Sector or division of the agricultural economy.\n        - name: group_desc\n          in: query\n          type: string\n          description: Commodity group description (e.g., FIELD CROPS, VEGETABLES).\n        - name: state_alpha\n          in: query\n          type: string\n          description: Two-letter state abbreviation (e.g., VA, IA, TX).\n        - name: state_name\n          in: query\n          type: string\n          description: Full state name.\n        - name: county_name\n          in: query\n          type: string\n          description: County name.\n        - name: agg_level_desc\n          in: query\n          type: string\n          description: Geographic aggregation level (NATIONAL, STATE, COUNTY, ZIP CODE).\n        - name: year\n          in: query\n          type: integer\n          description: Survey year (e.g., 2023). Supports operators like year__GE=2010.\n        - name: year__GE\n\
  \          in: query\n          type: integer\n          description: Year greater than or equal to specified value.\n        - name: year__LE\n          in: query\n          type: integer\n          description: Year less than or equal to specified value.\n        - name: freq_desc\n          in: query\n          type: string\n          description: Data collection frequency (ANNUAL, MONTHLY, WEEKLY, POINT IN TIME, SEASONAL).\n        - name: reference_period_desc\n          in: query\n          type: string\n          description: Reference period description (e.g., YEAR, JAN, JUN).\n        - name: format\n          in: query\n          type: string\n          description: Response format (JSON, XML, CSV). Defaults to JSON.\n        - name: callback\n          in: query\n          type: string\n          description: JSONP callback function name for cross-origin requests.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: get-param-values\n      path: /get_param_values\n      operations:\n      - name: getparamvalues\n        method: GET\n        description: USDA NASS Get Parameter Values\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: API key.\n        - name: param\n          in: query\n          type: string\n          required: true\n          description: The parameter name for which to return all valid values (e.g., commodity_desc, state_alpha, statisticcat_desc).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-counts\n      path: /get_counts\n      operations:\n      - name: getcounts\n        method: GET\n        description: USDA NASS Get Record Counts\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n       \
  \   description: API key.\n        - name: commodity_desc\n          in: query\n          type: string\n          description: Commodity description to count records for.\n        - name: state_alpha\n          in: query\n          type: string\n          description: State abbreviation to filter.\n        - name: year__GE\n          in: query\n          type: integer\n          description: Year filter (greater than or equal).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: agricultural-statistics-service-rest\n    description: REST adapter for USDA NASS QuickStats API.\n    resources:\n    - path: /api_GET\n      name: getstatistics\n      operations:\n      - method: GET\n        name: getstatistics\n        description: USDA NASS Get Statistics\n        call: agricultural-statistics-service.getstatistics\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /get_param_values\n      name: getparamvalues\n      operations:\n      - method: GET\n        name: getparamvalues\n        description: USDA NASS Get Parameter Values\n        call: agricultural-statistics-service.getparamvalues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_counts\n      name: getcounts\n      operations:\n      - method: GET\n        name: getcounts\n        description: USDA NASS Get Record Counts\n        call: agricultural-statistics-service.getcounts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: agricultural-statistics-service-mcp\n    transport: http\n    description: MCP adapter for USDA NASS QuickStats API for AI agent use.\n    tools:\n    - name: getstatistics\n      description: USDA NASS Get Statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: agricultural-statistics-service.getstatistics\n      with:\n        key: tools.key\n        commodity_desc: tools.commodity_desc\n        class_desc: tools.class_desc\n        statisticcat_desc: tools.statisticcat_desc\n        unit_desc: tools.unit_desc\n        sector_desc: tools.sector_desc\n        group_desc: tools.group_desc\n        state_alpha: tools.state_alpha\n        state_name: tools.state_name\n        county_name: tools.county_name\n        agg_level_desc: tools.agg_level_desc\n        year: tools.year\n        year__GE: tools.year__GE\n        year__LE: tools.year__LE\n        freq_desc: tools.freq_desc\n        reference_period_desc: tools.reference_period_desc\n        format: tools.format\n        callback: tools.callback\n      inputParameters:\n      - name: key\n        type: string\n        description: API key obtained by registering at the QuickStats API portal.\n        required: true\n      - name: commodity_desc\n        type: string\n        description:\
  \ Commodity description (e.g., CORN, SOYBEANS, CATTLE).\n      - name: class_desc\n        type: string\n        description: Commodity class description.\n      - name: statisticcat_desc\n        type: string\n        description: Statistical category (e.g., AREA HARVESTED, PRODUCTION, PRICE RECEIVED).\n      - name: unit_desc\n        type: string\n        description: Unit of measurement (e.g., ACRES, BU, HEAD).\n      - name: sector_desc\n        type: string\n        description: Sector or division of the agricultural economy.\n      - name: group_desc\n        type: string\n        description: Commodity group description (e.g., FIELD CROPS, VEGETABLES).\n      - name: state_alpha\n        type: string\n        description: Two-letter state abbreviation (e.g., VA, IA, TX).\n      - name: state_name\n        type: string\n        description: Full state name.\n      - name: county_name\n        type: string\n        description: County name.\n      - name: agg_level_desc\n       \
  \ type: string\n        description: Geographic aggregation level (NATIONAL, STATE, COUNTY, ZIP CODE).\n      - name: year\n        type: integer\n        description: Survey year (e.g., 2023). Supports operators like year__GE=2010.\n      - name: year__GE\n        type: integer\n        description: Year greater than or equal to specified value.\n      - name: year__LE\n        type: integer\n        description: Year less than or equal to specified value.\n      - name: freq_desc\n        type: string\n        description: Data collection frequency (ANNUAL, MONTHLY, WEEKLY, POINT IN TIME, SEASONAL).\n      - name: reference_period_desc\n        type: string\n        description: Reference period description (e.g., YEAR, JAN, JUN).\n      - name: format\n        type: string\n        description: Response format (JSON, XML, CSV). Defaults to JSON.\n      - name: callback\n        type: string\n        description: JSONP callback function name for cross-origin requests.\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getparamvalues\n      description: USDA NASS Get Parameter Values\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: agricultural-statistics-service.getparamvalues\n      with:\n        key: tools.key\n        param: tools.param\n      inputParameters:\n      - name: key\n        type: string\n        description: API key.\n        required: true\n      - name: param\n        type: string\n        description: The parameter name for which to return all valid values (e.g., commodity_desc, state_alpha, statisticcat_desc).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcounts\n      description: USDA NASS Get Record Counts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: agricultural-statistics-service.getcounts\n      with:\n        key: tools.key\n        commodity_desc:\
  \ tools.commodity_desc\n        state_alpha: tools.state_alpha\n        year__GE: tools.year__GE\n      inputParameters:\n      - name: key\n        type: string\n        description: API key.\n        required: true\n      - name: commodity_desc\n        type: string\n        description: Commodity description to count records for.\n      - name: state_alpha\n        type: string\n        description: State abbreviation to filter.\n      - name: year__GE\n        type: integer\n        description: Year filter (greater than or equal).\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AGRICULTURAL_STATISTICS_SERVICE_TOKEN: AGRICULTURAL_STATISTICS_SERVICE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/agricultural-statistics-service/refs/heads/main/capabilities/agricultural-statistics-service-capability.yaml
tags:
- Agricultural
- Statistics
- Service
- API
tools:
- description: USDA NASS Get Statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatistics
- description: USDA NASS Get Parameter Values
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getparamvalues
- description: USDA NASS Get Record Counts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcounts
---
