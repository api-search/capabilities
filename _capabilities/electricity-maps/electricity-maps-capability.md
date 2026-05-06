---
categories: []
consumed_apis: []
description: The Electricity Maps API delivers real-time, historical, and forecasted electricity grid signals worldwide, including carbon intensity, power breakdown by source, renewable and carbon-free percentages, electricity flows, total and net load, and day-ahead pricing. Each signal is available in three temporality variants (latest, past, forecast) and can be queried by zone identifier, geographic coordinates, or data center provider/region.
layout: capability
name: Electricity Maps API
operations:
- description: List available zones
  method: GET
  name: listzones
  path: /v3/zones
- description: Locate a zone by coordinates
  method: GET
  name: locatezone
  path: /v3/zone
- description: List available data centers
  method: GET
  name: listdatacenters
  path: /v3/data-centers
- description: Get carbon intensity signal
  method: GET
  name: getcarbonintensity
  path: /v3/carbon-intensity/{temporality}
- description: Get fossil-only carbon intensity
  method: GET
  name: getfossilonlycarbonintensity
  path: /v3/fossil-only-carbon-intensity/{temporality}
- description: Get electricity mix
  method: GET
  name: getelectricitymix
  path: /v3/electricity-mix/{temporality}
- description: Get renewable percentage
  method: GET
  name: getrenewablepercentage
  path: /v3/renewable-percentage/{temporality}
- description: Get carbon-free percentage
  method: GET
  name: getcarbonfreepercentage
  path: /v3/carbon-free-percentage/{temporality}
- description: Get total load
  method: GET
  name: gettotalload
  path: /v3/total-load/{temporality}
- description: Get net load
  method: GET
  name: getnetload
  path: /v3/net-load/{temporality}
- description: Get electricity flows
  method: GET
  name: getelectricityflows
  path: /v3/electricity-flows/{temporality}
- description: Get day-ahead price
  method: GET
  name: getdayaheadprice
  path: /v3/day-ahead-price/{temporality}
personas: []
provider_name: Electricity Maps
provider_slug: electricity-maps
search_terms:
- get fossil-only carbon intensity
- sustainability
- get carbon intensity signal
- carbon intensity
- get renewable percentage
- getrenewablepercentage
- getcarbonintensity
- getelectricitymix
- grid data
- locatezone
- get net load
- getdayaheadprice
- climate
- api
- gettotalload
- getelectricityflows
- getnetload
- maps
- get day-ahead price
- energy
- listdatacenters
- get total load
- list available data centers
- electricity
- listzones
- get electricity flows
- locate a zone by coordinates
- list available zones
- get carbon-free percentage
- getcarbonfreepercentage
- get electricity mix
- getfossilonlycarbonintensity
slug: electricity-maps-capability
source_filename: electricity-maps-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Electricity Maps API\n  description: The Electricity Maps API delivers real-time, historical, and forecasted electricity grid signals worldwide,\n    including carbon intensity, power breakdown by source, renewable and carbon-free percentages, electricity flows, total\n    and net load, and day-ahead pricing. Each signal is available in three temporality variants (latest, past, forecast) and\n    can be queried by zone identifier, geographic coordinates, or data center provider/region.\n  tags:\n  - Electricity\n  - Maps\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: electricity-maps\n    baseUri: https://api.electricitymap.org\n    description: Electricity Maps API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: auth-token\n      value: '{{ELECTRICITY_MAPS_TOKEN}}'\n    resources:\n    - name: v3-zones\n      path: /v3/zones\n    \
  \  operations:\n      - name: listzones\n        method: GET\n        description: List available zones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-zone\n      path: /v3/zone\n      operations:\n      - name: locatezone\n        method: GET\n        description: Locate a zone by coordinates\n        inputParameters:\n        - name: lon\n          in: query\n          type: number\n          required: true\n        - name: lat\n          in: query\n          type: number\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-data-centers\n      path: /v3/data-centers\n      operations:\n      - name: listdatacenters\n        method: GET\n        description: List available data centers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: v3-carbon-intensity-temporality\n      path: /v3/carbon-intensity/{temporality}\n      operations:\n      - name: getcarbonintensity\n        method: GET\n        description: Get carbon intensity signal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-fossil-only-carbon-intensity-temporality\n      path: /v3/fossil-only-carbon-intensity/{temporality}\n      operations:\n      - name: getfossilonlycarbonintensity\n        method: GET\n        description: Get fossil-only carbon intensity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-electricity-mix-temporality\n      path: /v3/electricity-mix/{temporality}\n      operations:\n      - name: getelectricitymix\n        method: GET\n        description: Get electricity mix\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-renewable-percentage-temporality\n      path: /v3/renewable-percentage/{temporality}\n      operations:\n      - name: getrenewablepercentage\n        method: GET\n        description: Get renewable percentage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-carbon-free-percentage-temporality\n      path: /v3/carbon-free-percentage/{temporality}\n      operations:\n      - name: getcarbonfreepercentage\n        method: GET\n        description: Get carbon-free percentage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-total-load-temporality\n      path: /v3/total-load/{temporality}\n      operations:\n      - name: gettotalload\n        method: GET\n        description: Get total load\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-net-load-temporality\n      path: /v3/net-load/{temporality}\n      operations:\n      - name: getnetload\n        method: GET\n        description: Get net load\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-electricity-flows-temporality\n      path: /v3/electricity-flows/{temporality}\n      operations:\n      - name: getelectricityflows\n        method: GET\n        description: Get electricity flows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v3-day-ahead-price-temporality\n      path: /v3/day-ahead-price/{temporality}\n      operations:\n      - name: getdayaheadprice\n        method: GET\n        description: Get day-ahead price\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: electricity-maps-rest\n    description: REST adapter for Electricity Maps API.\n    resources:\n    - path: /v3/zones\n      name: listzones\n      operations:\n      - method: GET\n        name: listzones\n        description: List available zones\n        call: electricity-maps.listzones\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/zone\n      name: locatezone\n      operations:\n      - method: GET\n        name: locatezone\n        description: Locate a zone by coordinates\n        call: electricity-maps.locatezone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/data-centers\n      name: listdatacenters\n      operations:\n      - method: GET\n        name: listdatacenters\n        description: List available data centers\n        call:\
  \ electricity-maps.listdatacenters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/carbon-intensity/{temporality}\n      name: getcarbonintensity\n      operations:\n      - method: GET\n        name: getcarbonintensity\n        description: Get carbon intensity signal\n        call: electricity-maps.getcarbonintensity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/fossil-only-carbon-intensity/{temporality}\n      name: getfossilonlycarbonintensity\n      operations:\n      - method: GET\n        name: getfossilonlycarbonintensity\n        description: Get fossil-only carbon intensity\n        call: electricity-maps.getfossilonlycarbonintensity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/electricity-mix/{temporality}\n      name: getelectricitymix\n      operations:\n      - method: GET\n        name: getelectricitymix\n        description: Get electricity\
  \ mix\n        call: electricity-maps.getelectricitymix\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/renewable-percentage/{temporality}\n      name: getrenewablepercentage\n      operations:\n      - method: GET\n        name: getrenewablepercentage\n        description: Get renewable percentage\n        call: electricity-maps.getrenewablepercentage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/carbon-free-percentage/{temporality}\n      name: getcarbonfreepercentage\n      operations:\n      - method: GET\n        name: getcarbonfreepercentage\n        description: Get carbon-free percentage\n        call: electricity-maps.getcarbonfreepercentage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/total-load/{temporality}\n      name: gettotalload\n      operations:\n      - method: GET\n        name: gettotalload\n        description: Get total load\n    \
  \    call: electricity-maps.gettotalload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/net-load/{temporality}\n      name: getnetload\n      operations:\n      - method: GET\n        name: getnetload\n        description: Get net load\n        call: electricity-maps.getnetload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/electricity-flows/{temporality}\n      name: getelectricityflows\n      operations:\n      - method: GET\n        name: getelectricityflows\n        description: Get electricity flows\n        call: electricity-maps.getelectricityflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v3/day-ahead-price/{temporality}\n      name: getdayaheadprice\n      operations:\n      - method: GET\n        name: getdayaheadprice\n        description: Get day-ahead price\n        call: electricity-maps.getdayaheadprice\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: electricity-maps-mcp\n    transport: http\n    description: MCP adapter for Electricity Maps API for AI agent use.\n    tools:\n    - name: listzones\n      description: List available zones\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.listzones\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: locatezone\n      description: Locate a zone by coordinates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.locatezone\n      with:\n        lon: tools.lon\n        lat: tools.lat\n      inputParameters:\n      - name: lon\n        type: number\n        description: lon\n        required: true\n      - name: lat\n        type: number\n        description: lat\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: listdatacenters\n      description: List available data centers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.listdatacenters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarbonintensity\n      description: Get carbon intensity signal\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.getcarbonintensity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfossilonlycarbonintensity\n      description: Get fossil-only carbon intensity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.getfossilonlycarbonintensity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getelectricitymix\n      description: Get electricity mix\n      hints:\n      \
  \  readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.getelectricitymix\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrenewablepercentage\n      description: Get renewable percentage\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.getrenewablepercentage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarbonfreepercentage\n      description: Get carbon-free percentage\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.getcarbonfreepercentage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettotalload\n      description: Get total load\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.gettotalload\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getnetload\n      description: Get net load\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.getnetload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getelectricityflows\n      description: Get electricity flows\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.getelectricityflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdayaheadprice\n      description: Get day-ahead price\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: electricity-maps.getdayaheadprice\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ELECTRICITY_MAPS_TOKEN: ELECTRICITY_MAPS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/electricity-maps/refs/heads/main/capabilities/electricity-maps-capability.yaml
tags:
- Electricity
- Maps
- API
tools:
- description: List available zones
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listzones
- description: Locate a zone by coordinates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: locatezone
- description: List available data centers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatacenters
- description: Get carbon intensity signal
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarbonintensity
- description: Get fossil-only carbon intensity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfossilonlycarbonintensity
- description: Get electricity mix
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getelectricitymix
- description: Get renewable percentage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrenewablepercentage
- description: Get carbon-free percentage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarbonfreepercentage
- description: Get total load
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettotalload
- description: Get net load
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnetload
- description: Get electricity flows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getelectricityflows
- description: Get day-ahead price
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdayaheadprice
---
