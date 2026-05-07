---
categories: []
consumed_apis: []
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
- acs 5-year demographic, economic, social, and housing estimates
- get acs1 demographics
- get official decennial census population counts from 2020 or 2010, with data by race/ethnicity at all geographic levels
- query acs 1-year demographic data for large geographies (65,000+ population) with more current estimates
- get acs 1-year estimates for geographies with 65,000+ population
- query business statistics
- query acs 5-year demographic data (population, income, education, housing) for any us geography from national down to block group level
- get annual population estimates for states and counties, including historical estimates back to the last decennial census
- get business patterns
- population
- geography
- query population estimates
- query demographic data
- decennial census population counts
- get annual population estimates using births, deaths, and migration data
- get population estimates
- get official decennial census population counts by geography and race
- get economic data on business establishments, employment counts, and payroll by industry (naics) and geography from county business patterns
- get acs5 demographics
- acs 1-year demographic estimates for large geographies
- get business establishment counts, employment, and payroll by industry
- annual population estimates by geography
- demographics
- get decennial data
- county business patterns economic data
- economics
- query acs 1year
- statistics
- federal government
- query decennial census
- open data
- get acs 5-year estimates for any us geography down to block group
slug: demographic-research
source_filename: demographic-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Census Bureau Demographic Research\n  description: Unified workflow capability for accessing U.S. Census Bureau statistical data for demographic research, economic\n    analysis, geographic enrichment, and population studies. Combines the Census Data API, Geocoding Services, and TIGERweb\n    geographic data into workflows for researchers, analysts, and application developers.\n  tags:\n  - Demographics\n  - Federal Government\n  - Open Data\n  - Statistics\n  - Population\n  - Economics\n  - Geography\n  created: '2026-05-03'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: census\n    baseUri: https://api.census.gov/data\n    description: U.S. Census Bureau Data API\n    resources:\n    - name: acs5\n      path: /{year}/acs/acs5\n      description: American Community Survey 5-Year Estimates\n      operations:\n      - name: get-acs5\n        method: GET\n        description: Returns ACS 5-Year demographic,\
  \ economic, social, and housing data\n        inputParameters:\n        - name: year\n          in: path\n          type: integer\n          required: true\n          description: ACS 5-Year end year (2009-2024)\n        - name: get\n          in: query\n          type: string\n          required: true\n          description: Comma-separated variable names to retrieve (max 50)\n        - name: for\n          in: query\n          type: string\n          required: false\n          description: Geography filter (e.g., state:06, county:*&in=state:06)\n        - name: in\n          in: query\n          type: string\n          required: false\n          description: Parent geography constraint for sub-state geographies\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: Census API key for higher usage limits\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value:\
  \ $.\n    - name: acs1\n      path: /{year}/acs/acs1\n      description: American Community Survey 1-Year Estimates\n      operations:\n      - name: get-acs1\n        method: GET\n        description: Returns ACS 1-Year data for geographies with 65,000+ population\n        inputParameters:\n        - name: year\n          in: path\n          type: integer\n          required: true\n          description: ACS 1-Year year (2005-2024)\n        - name: get\n          in: query\n          type: string\n          required: true\n          description: Comma-separated variable names to retrieve\n        - name: for\n          in: query\n          type: string\n          required: false\n          description: Geography filter\n        - name: in\n          in: query\n          type: string\n          required: false\n          description: Parent geography constraint\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: Census API\
  \ key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: decennial\n      path: /{year}/dec/pl\n      description: Decennial Census Redistricting Data\n      operations:\n      - name: get-decennial\n        method: GET\n        description: Returns Decennial Census population counts by race/ethnicity\n        inputParameters:\n        - name: year\n          in: path\n          type: integer\n          required: true\n          description: Census year (2020 or 2010)\n        - name: get\n          in: query\n          type: string\n          required: true\n          description: Variable names to retrieve\n        - name: for\n          in: query\n          type: string\n          required: false\n          description: Geography filter\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: Census API key\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: population-estimates\n      path: /{year}/pep/population\n      description: Annual Population Estimates\n      operations:\n      - name: get-population-estimates\n        method: GET\n        description: Returns annual population estimates for states and counties\n        inputParameters:\n        - name: year\n          in: path\n          type: integer\n          required: true\n          description: Estimates vintage year\n        - name: get\n          in: query\n          type: string\n          required: true\n          description: Variable names (e.g., NAME,POP,DATE_DESC)\n        - name: for\n          in: query\n          type: string\n          required: false\n          description: Geography filter\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: Census API key\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: cbp\n      path: /{year}/cbp\n      description: County Business Patterns\n      operations:\n      - name: get-county-business-patterns\n        method: GET\n        description: Returns business establishment, employment, and payroll data\n        inputParameters:\n        - name: year\n          in: path\n          type: integer\n          required: true\n          description: Data year (1986-2022)\n        - name: get\n          in: query\n          type: string\n          required: true\n          description: Variable names (e.g., NAME,NAICS2017,ESTAB,EMP,PAYANN)\n        - name: for\n          in: query\n          type: string\n          required: false\n          description: Geography filter\n        - name: key\n          in: query\n          type: string\n          required: false\n          description: Census API key\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: census-research-api\n    description: Unified REST API for Census Bureau demographic and economic data access.\n    resources:\n    - path: /v1/demographics/{year}/acs5\n      name: acs5-demographics\n      description: ACS 5-Year demographic, economic, social, and housing estimates\n      operations:\n      - method: GET\n        name: get-acs5-demographics\n        description: Get ACS 5-Year estimates for any US geography down to block group\n        call: census.get-acs5\n        with:\n          year: rest.year\n          get: rest.get\n          for: rest.for\n          in: rest.in\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/demographics/{year}/acs1\n      name: acs1-demographics\n      description: ACS 1-Year demographic estimates for large geographies\n      operations:\n      - method: GET\n        name: get-acs1-demographics\n\
  \        description: Get ACS 1-Year estimates for geographies with 65,000+ population\n        call: census.get-acs1\n        with:\n          year: rest.year\n          get: rest.get\n          for: rest.for\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/population/{year}/estimates\n      name: population-estimates\n      description: Annual population estimates by geography\n      operations:\n      - method: GET\n        name: get-population-estimates\n        description: Get annual population estimates using births, deaths, and migration data\n        call: census.get-population-estimates\n        with:\n          year: rest.year\n          get: rest.get\n          for: rest.for\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/census/{year}/decennial\n      name: decennial-counts\n      description: Decennial Census population counts\n      operations:\n      - method: GET\n        name: get-decennial-data\n\
  \        description: Get official Decennial Census population counts by geography and race\n        call: census.get-decennial\n        with:\n          year: rest.year\n          get: rest.get\n          for: rest.for\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/economy/{year}/business-patterns\n      name: business-patterns\n      description: County Business Patterns economic data\n      operations:\n      - method: GET\n        name: get-business-patterns\n        description: Get business establishment counts, employment, and payroll by industry\n        call: census.get-county-business-patterns\n        with:\n          year: rest.year\n          get: rest.get\n          for: rest.for\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: census-research-mcp\n    transport: http\n    description: MCP server for AI-assisted demographic research and census data analysis.\n\
  \    tools:\n    - name: query-demographic-data\n      description: Query ACS 5-Year demographic data (population, income, education, housing) for any US geography from national\n        down to block group level\n      hints:\n        readOnly: true\n        openWorld: true\n      call: census.get-acs5\n      with:\n        year: tools.year\n        get: tools.get\n        for: tools.for\n        in: tools.in\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: query-acs-1year\n      description: Query ACS 1-Year demographic data for large geographies (65,000+ population) with more current estimates\n      hints:\n        readOnly: true\n        openWorld: true\n      call: census.get-acs1\n      with:\n        year: tools.year\n        get: tools.get\n        for: tools.for\n        in: tools.in\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: query-population-estimates\n      description: Get annual population estimates for states\
  \ and counties, including historical estimates back to the last\n        decennial census\n      hints:\n        readOnly: true\n        openWorld: true\n      call: census.get-population-estimates\n      with:\n        year: tools.year\n        get: tools.get\n        for: tools.for\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: query-decennial-census\n      description: Get official Decennial Census population counts from 2020 or 2010, with data by race/ethnicity at all geographic\n        levels\n      hints:\n        readOnly: true\n        openWorld: true\n      call: census.get-decennial\n      with:\n        year: tools.year\n        get: tools.get\n        for: tools.for\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: query-business-statistics\n      description: Get economic data on business establishments, employment counts, and payroll by industry (NAICS) and geography\n        from County Business Patterns\n \
  \     hints:\n        readOnly: true\n        openWorld: true\n      call: census.get-county-business-patterns\n      with:\n        year: tools.year\n        get: tools.get\n        for: tools.for\n      outputParameters:\n      - type: array\n        mapping: $.\n"
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
