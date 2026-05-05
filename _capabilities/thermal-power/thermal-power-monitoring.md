---
categories: []
consumed_apis:
- thermal-power
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
- get hourly net generation by thermal fuel type (coal, gas, oil, nuclear) for regional grid operators (miso, pjm, caiso, ercot, spp, nyiso, isone).
- get hourly net generation by fuel type for grid regions.
- thermal generator capacity data.
- individual power plant fuel and generation metrics.
- get plant operations
- thermal power
- get nameplate and net capacity for individual thermal generators including prime mover type and energy source.
- natural gas
- power generation
- get hourly generation
- get generator capacity
- grid monitoring
- get monthly or annual electric power generation by thermal fuel type (coal, natural gas, petroleum, nuclear) and us state.
- get plant-level generation output, fuel consumption, heat content, and heat rate for individual thermal power plants.
- get nameplate and net capacity for thermal generating units.
- get electric power generation aggregated by fuel type and state.
- eia
- coal
- get rto hourly thermal generation
- get generation by fuel type
- nuclear
- get plant-level generation, fuel consumption, heat content, and heat rate.
- fuel analytics
- energy
- state-level generation and fuel consumption by thermal fuel type.
- electricity
- hourly rto/iso generation by thermal fuel type.
slug: thermal-power-monitoring
source_filename: thermal-power-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Thermal Power Monitoring\"\n  description: \"Workflow capability for monitoring thermal power generation assets including coal, natural gas, petroleum, and nuclear plants. Covers operational data, plant-level fuel metrics, generator capacity, and real-time RTO generation tracking.\"\n  tags:\n    - Energy\n    - Thermal Power\n    - Power Generation\n    - Electricity\n    - EIA\n    - Grid Monitoring\n    - Fuel Analytics\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      EIA_API_KEY: EIA_API_KEY\n\ncapability:\n  consumes:\n    - import: thermal-power\n      location: ./shared/thermal-power-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: thermal-power-monitoring-api\n      description: \"Unified REST API for thermal power generation monitoring and analytics.\"\n      resources:\n        - path: /v1/generation/by-fuel-type\n          name: generation-by-fuel-type\n\
  \          description: \"State-level generation and fuel consumption by thermal fuel type.\"\n          operations:\n            - method: GET\n              name: get-generation-by-fuel-type\n              description: \"Get electric power generation aggregated by fuel type and state.\"\n              call: \"thermal-power.get-electric-power-operational-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/plants/operations\n          name: plant-operations\n          description: \"Individual power plant fuel and generation metrics.\"\n          operations:\n            - method: GET\n              name: get-plant-operations\n              description: \"Get plant-level generation, fuel consumption, heat content, and heat rate.\"\n              call: \"thermal-power.get-facility-fuel-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path:\
  \ /v1/generators/capacity\n          name: generator-capacity\n          description: \"Thermal generator capacity data.\"\n          operations:\n            - method: GET\n              name: get-generator-capacity\n              description: \"Get nameplate and net capacity for thermal generating units.\"\n              call: \"thermal-power.get-operating-generator-capacity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/grid/hourly-generation\n          name: hourly-generation\n          description: \"Hourly RTO/ISO generation by thermal fuel type.\"\n          operations:\n            - method: GET\n              name: get-hourly-generation\n              description: \"Get hourly net generation by fuel type for grid regions.\"\n              call: \"thermal-power.get-rto-fuel-type-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n\
  \      port: 9090\n      namespace: thermal-power-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted thermal power generation monitoring and analytics.\"\n      tools:\n        - name: get-generation-by-fuel-type\n          description: \"Get monthly or annual electric power generation by thermal fuel type (coal, natural gas, petroleum, nuclear) and US state.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"thermal-power.get-electric-power-operational-data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-plant-operations\n          description: \"Get plant-level generation output, fuel consumption, heat content, and heat rate for individual thermal power plants.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"thermal-power.get-facility-fuel-data\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: get-generator-capacity\n          description: \"Get nameplate and net capacity for individual thermal generators including prime mover type and energy source.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"thermal-power.get-operating-generator-capacity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-rto-hourly-thermal-generation\n          description: \"Get hourly net generation by thermal fuel type (coal, gas, oil, nuclear) for regional grid operators (MISO, PJM, CAISO, ERCOT, SPP, NYISO, ISONE).\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"thermal-power.get-rto-fuel-type-data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
