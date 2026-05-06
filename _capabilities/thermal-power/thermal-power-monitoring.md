---
categories: []
consumed_apis: []
description: Workflow capability for monitoring thermal power generation assets including coal, natural gas, petroleum, and nuclear plants. Covers operational data, plant-level fuel metrics, generator capacity, and real-time RTO generation tracking.
layout: capability
name: Thermal Power Monitoring
operations:
- description: Get electric power generation aggregated by fuel type and state.
  method: GET
  name: get-generation-by-fuel-type
  path: /v1/generation/by-fuel-type
- description: Get plant-level generation, fuel consumption, heat content, and heat rate.
  method: GET
  name: get-plant-operations
  path: /v1/plants/operations
- description: Get nameplate and net capacity for thermal generating units.
  method: GET
  name: get-generator-capacity
  path: /v1/generators/capacity
- description: Get hourly net generation by fuel type for grid regions.
  method: GET
  name: get-hourly-generation
  path: /v1/grid/hourly-generation
personas: []
provider_name: Thermal Power
provider_slug: thermal-power
search_terms:
- grid monitoring
- get hourly net generation by fuel type for grid regions.
- get monthly or annual electric power generation by thermal fuel type (coal, natural gas, petroleum, nuclear) and us state.
- fuel analytics
- get generation by fuel type
- get plant-level generation output, fuel consumption, heat content, and heat rate for individual thermal power plants.
- state-level generation and fuel consumption by thermal fuel type.
- nuclear
- get rto hourly thermal generation
- get hourly net generation by thermal fuel type (coal, gas, oil, nuclear) for regional grid operators (miso, pjm, caiso, ercot, spp, nyiso, isone).
- eia
- individual power plant fuel and generation metrics.
- get nameplate and net capacity for thermal generating units.
- hourly rto/iso generation by thermal fuel type.
- get plant operations
- energy
- get nameplate and net capacity for individual thermal generators including prime mover type and energy source.
- power generation
- thermal generator capacity data.
- electricity
- get generator capacity
- coal
- thermal power
- get plant-level generation, fuel consumption, heat content, and heat rate.
- get hourly generation
- get electric power generation aggregated by fuel type and state.
- natural gas
slug: thermal-power-monitoring
source_filename: thermal-power-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Thermal Power Monitoring\n  description: Workflow capability for monitoring thermal power generation assets including coal, natural gas, petroleum,\n    and nuclear plants. Covers operational data, plant-level fuel metrics, generator capacity, and real-time RTO generation\n    tracking.\n  tags:\n  - Energy\n  - Thermal Power\n  - Power Generation\n  - Electricity\n  - EIA\n  - Grid Monitoring\n  - Fuel Analytics\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    EIA_API_KEY: EIA_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: thermal-power\n    baseUri: https://api.eia.gov/v2\n    description: EIA Open Data API v2 for thermal power generation data.\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{EIA_API_KEY}}'\n      placement: query\n    resources:\n    - name: electric-power-operational-data\n      path: /electricity/electric-power-operational-data/data\n\
  \      description: Aggregated electric power operational data by state, sector, and fuel type.\n      operations:\n      - name: get-electric-power-operational-data\n        method: GET\n        description: Retrieve electric power generation and fuel consumption by fuel type and state.\n        inputParameters:\n        - name: frequency\n          in: query\n          type: string\n          required: false\n          description: Data frequency (monthly, quarterly, annual).\n        - name: data[]\n          in: query\n          type: string\n          required: false\n          description: Data columns to return.\n        - name: facets[fueltypeid][]\n          in: query\n          type: string\n          required: false\n          description: Fuel type filter (COL, NG, PEL, NUC, ALL).\n        - name: facets[location][]\n          in: query\n          type: string\n          required: false\n          description: State abbreviation filter.\n        - name: start\n          in:\
  \ query\n          type: string\n          required: false\n          description: Start period YYYY-MM.\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End period YYYY-MM.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: length\n          in: query\n          type: integer\n          required: false\n          description: Records to return (max 5000).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: facility-fuel\n      path: /electricity/facility-fuel/data\n      description: Plant-level fuel consumption and generation data.\n      operations:\n      - name: get-facility-fuel-data\n        method: GET\n        description: Retrieve plant-level generation, fuel consumption, heat content, and heat rate.\n        inputParameters:\n\
  \        - name: frequency\n          in: query\n          type: string\n          required: false\n          description: Data frequency (monthly, annual).\n        - name: data[]\n          in: query\n          type: string\n          required: false\n          description: Data columns to return.\n        - name: facets[plantCode][]\n          in: query\n          type: string\n          required: false\n          description: EIA plant code filter.\n        - name: facets[fuel2002][]\n          in: query\n          type: string\n          required: false\n          description: Fuel type code filter.\n        - name: facets[state][]\n          in: query\n          type: string\n          required: false\n          description: State abbreviation filter.\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start period YYYY-MM.\n        - name: end\n          in: query\n          type: string\n          required: false\n\
  \          description: End period YYYY-MM.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: length\n          in: query\n          type: integer\n          required: false\n          description: Records to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: generator-capacity\n      path: /electricity/operating-generator-capacity/data\n      description: Individual generator nameplate and net capacity data.\n      operations:\n      - name: get-operating-generator-capacity\n        method: GET\n        description: Retrieve generator capacity, prime mover type, and energy source for thermal generating units.\n        inputParameters:\n        - name: frequency\n          in: query\n          type: string\n          required: false\n          description: Data frequency (monthly, annual).\n\
  \        - name: data[]\n          in: query\n          type: string\n          required: false\n          description: Data columns to return.\n        - name: facets[energy_source_code][]\n          in: query\n          type: string\n          required: false\n          description: Energy source code filter.\n        - name: facets[prime_mover_code][]\n          in: query\n          type: string\n          required: false\n          description: Prime mover code filter (ST, GT, IC, CA, CS).\n        - name: facets[stateid][]\n          in: query\n          type: string\n          required: false\n          description: State abbreviation filter.\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start period.\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End period.\n        - name: offset\n          in: query\n          type: integer\n         \
  \ required: false\n          description: Pagination offset.\n        - name: length\n          in: query\n          type: integer\n          required: false\n          description: Records to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rto-fuel-type\n      path: /electricity/rto/fuel-type-data/data\n      description: Hourly RTO/ISO generation by fuel type.\n      operations:\n      - name: get-rto-fuel-type-data\n        method: GET\n        description: Retrieve hourly net generation by fuel type for RTOs and ISOs.\n        inputParameters:\n        - name: frequency\n          in: query\n          type: string\n          required: false\n          description: Data frequency (hourly, local-hourly).\n        - name: data[]\n          in: query\n          type: string\n          required: false\n          description: Data columns to return.\n        - name: facets[respondent][]\n\
  \          in: query\n          type: string\n          required: false\n          description: RTO/ISO identifier (MISO, PJM, CAISO, ERCOT, SPP, NYISO, ISONE).\n        - name: facets[fueltype][]\n          in: query\n          type: string\n          required: false\n          description: Fuel type filter (NG, COL, OIL, NUC).\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start datetime YYYY-MM-DDTHH.\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End datetime YYYY-MM-DDTHH.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: length\n          in: query\n          type: integer\n          required: false\n          description: Records to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: thermal-power-monitoring-api\n    description: Unified REST API for thermal power generation monitoring and analytics.\n    resources:\n    - path: /v1/generation/by-fuel-type\n      name: generation-by-fuel-type\n      description: State-level generation and fuel consumption by thermal fuel type.\n      operations:\n      - method: GET\n        name: get-generation-by-fuel-type\n        description: Get electric power generation aggregated by fuel type and state.\n        call: thermal-power.get-electric-power-operational-data\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plants/operations\n      name: plant-operations\n      description: Individual power plant fuel and generation metrics.\n      operations:\n      - method: GET\n        name: get-plant-operations\n        description: Get plant-level generation, fuel consumption, heat content, and heat\
  \ rate.\n        call: thermal-power.get-facility-fuel-data\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/generators/capacity\n      name: generator-capacity\n      description: Thermal generator capacity data.\n      operations:\n      - method: GET\n        name: get-generator-capacity\n        description: Get nameplate and net capacity for thermal generating units.\n        call: thermal-power.get-operating-generator-capacity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/grid/hourly-generation\n      name: hourly-generation\n      description: Hourly RTO/ISO generation by thermal fuel type.\n      operations:\n      - method: GET\n        name: get-hourly-generation\n        description: Get hourly net generation by fuel type for grid regions.\n        call: thermal-power.get-rto-fuel-type-data\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port:\
  \ 9090\n    namespace: thermal-power-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted thermal power generation monitoring and analytics.\n    tools:\n    - name: get-generation-by-fuel-type\n      description: Get monthly or annual electric power generation by thermal fuel type (coal, natural gas, petroleum, nuclear)\n        and US state.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: thermal-power.get-electric-power-operational-data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-plant-operations\n      description: Get plant-level generation output, fuel consumption, heat content, and heat rate for individual thermal\n        power plants.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: thermal-power.get-facility-fuel-data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-generator-capacity\n      description: Get nameplate\
  \ and net capacity for individual thermal generators including prime mover type and energy\n        source.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: thermal-power.get-operating-generator-capacity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rto-hourly-thermal-generation\n      description: Get hourly net generation by thermal fuel type (coal, gas, oil, nuclear) for regional grid operators (MISO,\n        PJM, CAISO, ERCOT, SPP, NYISO, ISONE).\n      hints:\n        readOnly: true\n        idempotent: true\n      call: thermal-power.get-rto-fuel-type-data\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/thermal-power/refs/heads/main/capabilities/thermal-power-monitoring.yaml
tags:
- Energy
- Thermal Power
- Power Generation
- Electricity
- EIA
- Grid Monitoring
- Fuel Analytics
tools:
- description: Get monthly or annual electric power generation by thermal fuel type (coal, natural gas, petroleum, nuclear) and US state.
  hints:
    idempotent: true
    readOnly: true
  name: get-generation-by-fuel-type
- description: Get plant-level generation output, fuel consumption, heat content, and heat rate for individual thermal power plants.
  hints:
    idempotent: true
    readOnly: true
  name: get-plant-operations
- description: Get nameplate and net capacity for individual thermal generators including prime mover type and energy source.
  hints:
    idempotent: true
    readOnly: true
  name: get-generator-capacity
- description: Get hourly net generation by thermal fuel type (coal, gas, oil, nuclear) for regional grid operators (MISO, PJM, CAISO, ERCOT, SPP, NYISO, ISONE).
  hints:
    idempotent: true
    readOnly: true
  name: get-rto-hourly-thermal-generation
---
