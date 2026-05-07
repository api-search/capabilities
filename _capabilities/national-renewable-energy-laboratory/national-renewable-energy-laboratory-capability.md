---
categories: []
consumed_apis: []
description: Selected endpoints from the National Renewable Energy Laboratory (NREL) developer network covering alternative fuel stations, solar resource and PV modeling, and utility electricity rate lookups. All endpoints require a developer API key.
layout: capability
name: NREL Developer Network APIs
operations:
- description: Search alternative fuel stations
  method: GET
  name: get-alt-fuel-stations-v1-json
  path: /alt-fuel-stations/v1.json
- description: Find nearest alternative fuel stations
  method: GET
  name: get-alt-fuel-stations-v1-nearest-json
  path: /alt-fuel-stations/v1/nearest.json
- description: PVWatts solar PV system production estimate
  method: GET
  name: get-pvwatts-v8-json
  path: /pvwatts/v8.json
- description: Utility electricity rates by location
  method: GET
  name: get-utility-rates-v3-json
  path: /utility_rates/v3.json
- description: Solar resource data
  method: GET
  name: get-solar-solar-resource-v1-json
  path: /solar/solar_resource/v1.json
personas: []
provider_name: National Renewable Energy Laboratory
provider_slug: national-renewable-energy-laboratory
search_terms:
- laboratory
- get solar solar resource v1 json
- api
- get utility rates v3 json
- research
- get alt fuel stations v1 nearest json
- energy
- utility electricity rates by location
- renewable energy
- climate
- get alt fuel stations v1 json
- find nearest alternative fuel stations
- national
- renewable
- search alternative fuel stations
- get pvwatts v8 json
- federal government
- pvwatts solar pv system production estimate
- solar resource data
slug: national-renewable-energy-laboratory-capability
source_filename: national-renewable-energy-laboratory-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NREL Developer Network APIs\n  description: Selected endpoints from the National Renewable Energy Laboratory (NREL) developer network covering alternative\n    fuel stations, solar resource and PV modeling, and utility electricity rate lookups. All endpoints require a developer\n    API key.\n  tags:\n  - National\n  - Renewable\n  - Energy\n  - Laboratory\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: national-renewable-energy-laboratory\n    baseUri: https://developer.nrel.gov/api\n    description: NREL Developer Network APIs HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_key\n      value: '{{NATIONAL_RENEWABLE_ENERGY_LABORATORY_TOKEN}}'\n    resources:\n    - name: alt-fuel-stations-v1-json\n      path: /alt-fuel-stations/v1.json\n      operations:\n      - name: get-alt-fuel-stations-v1-json\n        method: GET\n        description:\
  \ Search alternative fuel stations\n        inputParameters:\n        - name: fuel_type\n          in: query\n          type: string\n          description: Comma-separated list (e.g., ELEC,LPG,CNG).\n        - name: state\n          in: query\n          type: string\n        - name: zip\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        - name: access\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alt-fuel-stations-v1-nearest-json\n      path: /alt-fuel-stations/v1/nearest.json\n      operations:\n      - name: get-alt-fuel-stations-v1-nearest-json\n        method: GET\n        description: Find nearest alternative fuel stations\n        inputParameters:\n        - name: location\n          in: query\n        \
  \  type: string\n          description: Address or place name.\n        - name: latitude\n          in: query\n          type: number\n        - name: longitude\n          in: query\n          type: number\n        - name: radius\n          in: query\n          type: number\n          description: Search radius in miles.\n        - name: fuel_type\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pvwatts-v8-json\n      path: /pvwatts/v8.json\n      operations:\n      - name: get-pvwatts-v8-json\n        method: GET\n        description: PVWatts solar PV system production estimate\n        inputParameters:\n        - name: system_capacity\n          in: query\n          type: number\n          required: true\n          description: System size in kW DC.\n        - name: module_type\n          in: query\n          type: integer\n          required: true\n\
  \        - name: losses\n          in: query\n          type: number\n          required: true\n        - name: array_type\n          in: query\n          type: integer\n          required: true\n        - name: tilt\n          in: query\n          type: number\n          required: true\n        - name: azimuth\n          in: query\n          type: number\n          required: true\n        - name: address\n          in: query\n          type: string\n        - name: lat\n          in: query\n          type: number\n        - name: lon\n          in: query\n          type: number\n        - name: timeframe\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: utility-rates-v3-json\n      path: /utility_rates/v3.json\n      operations:\n      - name: get-utility-rates-v3-json\n        method: GET\n        description: Utility electricity rates by location\n \
  \       inputParameters:\n        - name: address\n          in: query\n          type: string\n        - name: lat\n          in: query\n          type: number\n        - name: lon\n          in: query\n          type: number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: solar-solar-resource-v1-json\n      path: /solar/solar_resource/v1.json\n      operations:\n      - name: get-solar-solar-resource-v1-json\n        method: GET\n        description: Solar resource data\n        inputParameters:\n        - name: address\n          in: query\n          type: string\n        - name: lat\n          in: query\n          type: number\n        - name: lon\n          in: query\n          type: number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: national-renewable-energy-laboratory-rest\n\
  \    description: REST adapter for NREL Developer Network APIs.\n    resources:\n    - path: /alt-fuel-stations/v1.json\n      name: get-alt-fuel-stations-v1-json\n      operations:\n      - method: GET\n        name: get-alt-fuel-stations-v1-json\n        description: Search alternative fuel stations\n        call: national-renewable-energy-laboratory.get-alt-fuel-stations-v1-json\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alt-fuel-stations/v1/nearest.json\n      name: get-alt-fuel-stations-v1-nearest-json\n      operations:\n      - method: GET\n        name: get-alt-fuel-stations-v1-nearest-json\n        description: Find nearest alternative fuel stations\n        call: national-renewable-energy-laboratory.get-alt-fuel-stations-v1-nearest-json\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pvwatts/v8.json\n      name: get-pvwatts-v8-json\n      operations:\n      - method: GET\n        name: get-pvwatts-v8-json\n\
  \        description: PVWatts solar PV system production estimate\n        call: national-renewable-energy-laboratory.get-pvwatts-v8-json\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /utility_rates/v3.json\n      name: get-utility-rates-v3-json\n      operations:\n      - method: GET\n        name: get-utility-rates-v3-json\n        description: Utility electricity rates by location\n        call: national-renewable-energy-laboratory.get-utility-rates-v3-json\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /solar/solar_resource/v1.json\n      name: get-solar-solar-resource-v1-json\n      operations:\n      - method: GET\n        name: get-solar-solar-resource-v1-json\n        description: Solar resource data\n        call: national-renewable-energy-laboratory.get-solar-solar-resource-v1-json\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace:\
  \ national-renewable-energy-laboratory-mcp\n    transport: http\n    description: MCP adapter for NREL Developer Network APIs for AI agent use.\n    tools:\n    - name: get-alt-fuel-stations-v1-json\n      description: Search alternative fuel stations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-renewable-energy-laboratory.get-alt-fuel-stations-v1-json\n      with:\n        fuel_type: tools.fuel_type\n        state: tools.state\n        zip: tools.zip\n        status: tools.status\n        access: tools.access\n        limit: tools.limit\n      inputParameters:\n      - name: fuel_type\n        type: string\n        description: Comma-separated list (e.g., ELEC,LPG,CNG).\n      - name: state\n        type: string\n        description: state\n      - name: zip\n        type: string\n        description: zip\n      - name: status\n        type: string\n        description: status\n      - name: access\n        type: string\n\
  \        description: access\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alt-fuel-stations-v1-nearest-json\n      description: Find nearest alternative fuel stations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-renewable-energy-laboratory.get-alt-fuel-stations-v1-nearest-json\n      with:\n        location: tools.location\n        latitude: tools.latitude\n        longitude: tools.longitude\n        radius: tools.radius\n        fuel_type: tools.fuel_type\n      inputParameters:\n      - name: location\n        type: string\n        description: Address or place name.\n      - name: latitude\n        type: number\n        description: latitude\n      - name: longitude\n        type: number\n        description: longitude\n      - name: radius\n        type: number\n        description: Search radius in miles.\n\
  \      - name: fuel_type\n        type: string\n        description: fuel_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pvwatts-v8-json\n      description: PVWatts solar PV system production estimate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-renewable-energy-laboratory.get-pvwatts-v8-json\n      with:\n        system_capacity: tools.system_capacity\n        module_type: tools.module_type\n        losses: tools.losses\n        array_type: tools.array_type\n        tilt: tools.tilt\n        azimuth: tools.azimuth\n        address: tools.address\n        lat: tools.lat\n        lon: tools.lon\n        timeframe: tools.timeframe\n      inputParameters:\n      - name: system_capacity\n        type: number\n        description: System size in kW DC.\n        required: true\n      - name: module_type\n        type: integer\n        description: module_type\n        required: true\n\
  \      - name: losses\n        type: number\n        description: losses\n        required: true\n      - name: array_type\n        type: integer\n        description: array_type\n        required: true\n      - name: tilt\n        type: number\n        description: tilt\n        required: true\n      - name: azimuth\n        type: number\n        description: azimuth\n        required: true\n      - name: address\n        type: string\n        description: address\n      - name: lat\n        type: number\n        description: lat\n      - name: lon\n        type: number\n        description: lon\n      - name: timeframe\n        type: string\n        description: timeframe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-utility-rates-v3-json\n      description: Utility electricity rates by location\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-renewable-energy-laboratory.get-utility-rates-v3-json\n\
  \      with:\n        address: tools.address\n        lat: tools.lat\n        lon: tools.lon\n      inputParameters:\n      - name: address\n        type: string\n        description: address\n      - name: lat\n        type: number\n        description: lat\n      - name: lon\n        type: number\n        description: lon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-solar-solar-resource-v1-json\n      description: Solar resource data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-renewable-energy-laboratory.get-solar-solar-resource-v1-json\n      with:\n        address: tools.address\n        lat: tools.lat\n        lon: tools.lon\n      inputParameters:\n      - name: address\n        type: string\n        description: address\n      - name: lat\n        type: number\n        description: lat\n      - name: lon\n        type: number\n        description: lon\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NATIONAL_RENEWABLE_ENERGY_LABORATORY_TOKEN: NATIONAL_RENEWABLE_ENERGY_LABORATORY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/national-renewable-energy-laboratory/refs/heads/main/capabilities/national-renewable-energy-laboratory-capability.yaml
tags:
- National
- Renewable
- Energy
- Laboratory
- API
tools:
- description: Search alternative fuel stations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-alt-fuel-stations-v1-json
- description: Find nearest alternative fuel stations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-alt-fuel-stations-v1-nearest-json
- description: PVWatts solar PV system production estimate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-pvwatts-v8-json
- description: Utility electricity rates by location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-utility-rates-v3-json
- description: Solar resource data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-solar-solar-resource-v1-json
---
