---
api_specs:
- filename: census-data-api-openapi.yml
  format: yaml
  label: census
  slug: census
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/united-states-census-bureau/refs/heads/main/openapi/census-data-api-openapi.yml
categories: []
consumed_apis:
- census
description: Unified workflow capability for accessing U.S. Census Bureau statistical data for demographic research, economic analysis, geographic enrichment, and population studies. Combines the Census Data API, Geocoding Services, and TIGERweb geographic data into workflows for researchers, analysts, and application developers.
layout: capability
name: Census Bureau Demographic Research
operations:
- description: Get ACS 5-Year estimates for any US geography down to block group
  method: GET
  name: get-acs5-demographics
  path: /v1/demographics/{year}/acs5
- description: Get ACS 1-Year estimates for geographies with 65,000+ population
  method: GET
  name: get-acs1-demographics
  path: /v1/demographics/{year}/acs1
- description: Get annual population estimates using births, deaths, and migration data
  method: GET
  name: get-population-estimates
  path: /v1/population/{year}/estimates
- description: Get official Decennial Census population counts by geography and race
  method: GET
  name: get-decennial-data
  path: /v1/census/{year}/decennial
- description: Get business establishment counts, employment, and payroll by industry
  method: GET
  name: get-business-patterns
  path: /v1/economy/{year}/business-patterns
personas: []
provider_name: United States Census Bureau
provider_slug: united-states-census-bureau
search_terms:
- open data
- get business patterns
- query business statistics
- federal government
- get population estimates
- get official decennial census population counts from 2020 or 2010, with data by race/ethnicity at all geographic levels
- acs 1-year demographic estimates for large geographies
- economics
- get business establishment counts, employment, and payroll by industry
- acs 5-year demographic, economic, social, and housing estimates
- query acs 1year
- annual population estimates by geography
- get annual population estimates for states and counties, including historical estimates back to the last decennial census
- get acs 1-year estimates for geographies with 65,000+ population
- demographics
- get decennial data
- statistics
- decennial census population counts
- population
- query population estimates
- county business patterns economic data
- get annual population estimates using births, deaths, and migration data
- get official decennial census population counts by geography and race
- query decennial census
- query acs 1-year demographic data for large geographies (65,000+ population) with more current estimates
- geography
- query demographic data
- get economic data on business establishments, employment counts, and payroll by industry (naics) and geography from county business patterns
- get acs5 demographics
- get acs1 demographics
- get acs 5-year estimates for any us geography down to block group
- query acs 5-year demographic data (population, income, education, housing) for any us geography from national down to block group level
slug: demographic-research
source_filename: demographic-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Census Bureau Demographic Research\"\n  description: >-\n    Unified workflow capability for accessing U.S. Census Bureau statistical data\n    for demographic research, economic analysis, geographic enrichment, and\n    population studies. Combines the Census Data API, Geocoding Services, and\n    TIGERweb geographic data into workflows for researchers, analysts, and\n    application developers.\n  tags:\n    - Demographics\n    - Federal Government\n    - Open Data\n    - Statistics\n    - Population\n    - Economics\n    - Geography\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\ncapability:\n  consumes:\n    - import: census\n      location: ./shared/census-data-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: census-research-api\n      description: \"Unified REST API for Census Bureau demographic and economic data access.\"\n      resources:\n        - path: /v1/demographics/{year}/acs5\n\
  \          name: acs5-demographics\n          description: \"ACS 5-Year demographic, economic, social, and housing estimates\"\n          operations:\n            - method: GET\n              name: get-acs5-demographics\n              description: \"Get ACS 5-Year estimates for any US geography down to block group\"\n              call: \"census.get-acs5\"\n              with:\n                year: \"rest.year\"\n                get: \"rest.get\"\n                for: \"rest.for\"\n                in: \"rest.in\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/demographics/{year}/acs1\n          name: acs1-demographics\n          description: \"ACS 1-Year demographic estimates for large geographies\"\n          operations:\n            - method: GET\n              name: get-acs1-demographics\n              description: \"Get ACS 1-Year estimates for geographies with 65,000+ population\"\n              call: \"census.get-acs1\"\
  \n              with:\n                year: \"rest.year\"\n                get: \"rest.get\"\n                for: \"rest.for\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/population/{year}/estimates\n          name: population-estimates\n          description: \"Annual population estimates by geography\"\n          operations:\n            - method: GET\n              name: get-population-estimates\n              description: \"Get annual population estimates using births, deaths, and migration data\"\n              call: \"census.get-population-estimates\"\n              with:\n                year: \"rest.year\"\n                get: \"rest.get\"\n                for: \"rest.for\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/census/{year}/decennial\n          name: decennial-counts\n          description: \"Decennial Census population\
  \ counts\"\n          operations:\n            - method: GET\n              name: get-decennial-data\n              description: \"Get official Decennial Census population counts by geography and race\"\n              call: \"census.get-decennial\"\n              with:\n                year: \"rest.year\"\n                get: \"rest.get\"\n                for: \"rest.for\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/economy/{year}/business-patterns\n          name: business-patterns\n          description: \"County Business Patterns economic data\"\n          operations:\n            - method: GET\n              name: get-business-patterns\n              description: \"Get business establishment counts, employment, and payroll by industry\"\n              call: \"census.get-county-business-patterns\"\n              with:\n                year: \"rest.year\"\n                get: \"rest.get\"\n              \
  \  for: \"rest.for\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: census-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted demographic research and census data analysis.\"\n      tools:\n        - name: query-demographic-data\n          description: \"Query ACS 5-Year demographic data (population, income, education, housing) for any US geography from national down to block group level\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"census.get-acs5\"\n          with:\n            year: \"tools.year\"\n            get: \"tools.get\"\n            for: \"tools.for\"\n            in: \"tools.in\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: query-acs-1year\n          description: \"Query ACS 1-Year demographic data for large geographies (65,000+\
  \ population) with more current estimates\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"census.get-acs1\"\n          with:\n            year: \"tools.year\"\n            get: \"tools.get\"\n            for: \"tools.for\"\n            in: \"tools.in\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: query-population-estimates\n          description: \"Get annual population estimates for states and counties, including historical estimates back to the last decennial census\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"census.get-population-estimates\"\n          with:\n            year: \"tools.year\"\n            get: \"tools.get\"\n            for: \"tools.for\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: query-decennial-census\n          description: \"Get official Decennial\
  \ Census population counts from 2020 or 2010, with data by race/ethnicity at all geographic levels\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"census.get-decennial\"\n          with:\n            year: \"tools.year\"\n            get: \"tools.get\"\n            for: \"tools.for\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: query-business-statistics\n          description: \"Get economic data on business establishments, employment counts, and payroll by industry (NAICS) and geography from County Business Patterns\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"census.get-county-business-patterns\"\n          with:\n            year: \"tools.year\"\n            get: \"tools.get\"\n            for: \"tools.for\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-states-census-bureau/refs/heads/main/capabilities/demographic-research.yaml
tags:
- Demographics
- Federal Government
- Open Data
- Statistics
- Population
- Economics
- Geography
tools:
- description: Query ACS 5-Year demographic data (population, income, education, housing) for any US geography from national down to block group level
  hints:
    openWorld: true
    readOnly: true
  name: query-demographic-data
- description: Query ACS 1-Year demographic data for large geographies (65,000+ population) with more current estimates
  hints:
    openWorld: true
    readOnly: true
  name: query-acs-1year
- description: Get annual population estimates for states and counties, including historical estimates back to the last decennial census
  hints:
    openWorld: true
    readOnly: true
  name: query-population-estimates
- description: Get official Decennial Census population counts from 2020 or 2010, with data by race/ethnicity at all geographic levels
  hints:
    openWorld: true
    readOnly: true
  name: query-decennial-census
- description: Get economic data on business establishments, employment counts, and payroll by industry (NAICS) and geography from County Business Patterns
  hints:
    openWorld: true
    readOnly: true
  name: query-business-statistics
---
