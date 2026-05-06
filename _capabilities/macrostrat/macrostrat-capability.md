---
categories: []
consumed_apis: []
description: Macrostrat is a platform for the aggregation and distribution of geological data relevant to the spatial and temporal distribution of sedimentary, igneous, and metamorphic rocks as well as data extracted from them. The API provides programmatic access to columns, units, fossils, geologic maps, paleogeography, measurements, and statistics.
layout: capability
name: Macrostrat API
operations:
- description: Search columns
  method: GET
  name: getcolumns
  path: /columns
- description: Summarize sections
  method: GET
  name: getsections
  path: /sections
- description: Search units
  method: GET
  name: getunits
  path: /units
- description: Search fossils
  method: GET
  name: getfossils
  path: /fossils
- description: Get database statistics
  method: GET
  name: getstats
  path: /stats
- description: Get paleogeography reconstructions
  method: GET
  name: getpaleogeography
  path: /paleogeography
- description: Geologic map units
  method: GET
  name: getgeologicmapunits
  path: /geologic_units/map
- description: Geologic map point features
  method: GET
  name: getgeologicmappoints
  path: /geologic_units/map/points
- description: Geologic map legend
  method: GET
  name: getgeologicmaplegend
  path: /geologic_units/map/legend
- description: Get measurements
  method: GET
  name: getmeasurements
  path: /measurements
- description: Get age model
  method: GET
  name: getagemodel
  path: /age_model
- description: Standard definitions
  method: GET
  name: getdefs
  path: /defs
- description: Geologic map creation
  method: GET
  name: getcarto
  path: /carto
- description: Get grid data
  method: GET
  name: getgrids
  path: /grids
- description: Mobile data delivery
  method: GET
  name: getmobile
  path: /mobile
- description: API metadata
  method: GET
  name: getmeta
  path: /meta
personas: []
provider_name: Macrostrat
provider_slug: macrostrat
search_terms:
- search columns
- get database statistics
- search fossils
- earth science
- geology
- getunits
- geological data
- getcolumns
- paleontology
- getdefs
- summarize sections
- mobile data delivery
- getgeologicmapunits
- getpaleogeography
- get grid data
- getmobile
- getmeasurements
- geologic map point features
- search units
- getgeologicmappoints
- geologic map units
- getgrids
- api metadata
- standard definitions
- api
- get paleogeography reconstructions
- getstats
- geologic map creation
- getmeta
- getgeologicmaplegend
- macrostrat
- getsections
- get measurements
- getfossils
- rocks
- getagemodel
- get age model
- geologic map legend
- getcarto
slug: macrostrat-capability
source_filename: macrostrat-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Macrostrat API\n  description: Macrostrat is a platform for the aggregation and distribution of geological data relevant to the spatial and\n    temporal distribution of sedimentary, igneous, and metamorphic rocks as well as data extracted from them. The API provides\n    programmatic access to columns, units, fossils, geologic maps, paleogeography, measurements, and statistics.\n  tags:\n  - Macrostrat\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: macrostrat\n    baseUri: https://macrostrat.org/api/v2\n    description: Macrostrat API HTTP API.\n    resources:\n    - name: columns\n      path: /columns\n      operations:\n      - name: getcolumns\n        method: GET\n        description: Search columns\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        - name: lat\n          in: query\n          type: number\n \
  \       - name: lng\n          in: query\n          type: number\n        - name: age\n          in: query\n          type: number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sections\n      path: /sections\n      operations:\n      - name: getsections\n        method: GET\n        description: Summarize sections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: units\n      path: /units\n      operations:\n      - name: getunits\n        method: GET\n        description: Search units\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        - name: interval_name\n          in: query\n          type: string\n        - name: lith\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: fossils\n      path: /fossils\n      operations:\n      - name: getfossils\n        method: GET\n        description: Search fossils\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats\n      path: /stats\n      operations:\n      - name: getstats\n        method: GET\n        description: Get database statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: paleogeography\n      path: /paleogeography\n      operations:\n      - name: getpaleogeography\n        method: GET\n        description: Get paleogeography reconstructions\n        inputParameters:\n        - name: age\n          in: query\n          type: number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: geologic-units-map\n      path: /geologic_units/map\n      operations:\n      - name: getgeologicmapunits\n        method: GET\n        description: Geologic map units\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: geologic-units-map-points\n      path: /geologic_units/map/points\n      operations:\n      - name: getgeologicmappoints\n        method: GET\n        description: Geologic map point features\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: geologic-units-map-legend\n      path: /geologic_units/map/legend\n      operations:\n      - name: getgeologicmaplegend\n        method: GET\n        description: Geologic map legend\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: measurements\n      path:\
  \ /measurements\n      operations:\n      - name: getmeasurements\n        method: GET\n        description: Get measurements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: age-model\n      path: /age_model\n      operations:\n      - name: getagemodel\n        method: GET\n        description: Get age model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: defs\n      path: /defs\n      operations:\n      - name: getdefs\n        method: GET\n        description: Standard definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carto\n      path: /carto\n      operations:\n      - name: getcarto\n        method: GET\n        description: Geologic map creation\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: grids\n      path: /grids\n      operations:\n      - name: getgrids\n        method: GET\n        description: Get grid data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mobile\n      path: /mobile\n      operations:\n      - name: getmobile\n        method: GET\n        description: Mobile data delivery\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meta\n      path: /meta\n      operations:\n      - name: getmeta\n        method: GET\n        description: API metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: macrostrat-rest\n    description: REST adapter for Macrostrat API.\n\
  \    resources:\n    - path: /columns\n      name: getcolumns\n      operations:\n      - method: GET\n        name: getcolumns\n        description: Search columns\n        call: macrostrat.getcolumns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sections\n      name: getsections\n      operations:\n      - method: GET\n        name: getsections\n        description: Summarize sections\n        call: macrostrat.getsections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /units\n      name: getunits\n      operations:\n      - method: GET\n        name: getunits\n        description: Search units\n        call: macrostrat.getunits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fossils\n      name: getfossils\n      operations:\n      - method: GET\n        name: getfossils\n        description: Search fossils\n        call: macrostrat.getfossils\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /stats\n      name: getstats\n      operations:\n      - method: GET\n        name: getstats\n        description: Get database statistics\n        call: macrostrat.getstats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /paleogeography\n      name: getpaleogeography\n      operations:\n      - method: GET\n        name: getpaleogeography\n        description: Get paleogeography reconstructions\n        call: macrostrat.getpaleogeography\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /geologic_units/map\n      name: getgeologicmapunits\n      operations:\n      - method: GET\n        name: getgeologicmapunits\n        description: Geologic map units\n        call: macrostrat.getgeologicmapunits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /geologic_units/map/points\n      name: getgeologicmappoints\n      operations:\n\
  \      - method: GET\n        name: getgeologicmappoints\n        description: Geologic map point features\n        call: macrostrat.getgeologicmappoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /geologic_units/map/legend\n      name: getgeologicmaplegend\n      operations:\n      - method: GET\n        name: getgeologicmaplegend\n        description: Geologic map legend\n        call: macrostrat.getgeologicmaplegend\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /measurements\n      name: getmeasurements\n      operations:\n      - method: GET\n        name: getmeasurements\n        description: Get measurements\n        call: macrostrat.getmeasurements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /age_model\n      name: getagemodel\n      operations:\n      - method: GET\n        name: getagemodel\n        description: Get age model\n        call: macrostrat.getagemodel\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /defs\n      name: getdefs\n      operations:\n      - method: GET\n        name: getdefs\n        description: Standard definitions\n        call: macrostrat.getdefs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carto\n      name: getcarto\n      operations:\n      - method: GET\n        name: getcarto\n        description: Geologic map creation\n        call: macrostrat.getcarto\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /grids\n      name: getgrids\n      operations:\n      - method: GET\n        name: getgrids\n        description: Get grid data\n        call: macrostrat.getgrids\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mobile\n      name: getmobile\n      operations:\n      - method: GET\n        name: getmobile\n        description: Mobile data delivery\n        call:\
  \ macrostrat.getmobile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /meta\n      name: getmeta\n      operations:\n      - method: GET\n        name: getmeta\n        description: API metadata\n        call: macrostrat.getmeta\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: macrostrat-mcp\n    transport: http\n    description: MCP adapter for Macrostrat API for AI agent use.\n    tools:\n    - name: getcolumns\n      description: Search columns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getcolumns\n      with:\n        format: tools.format\n        lat: tools.lat\n        lng: tools.lng\n        age: tools.age\n      inputParameters:\n      - name: format\n        type: string\n        description: format\n      - name: lat\n        type: number\n        description: lat\n      - name: lng\n        type:\
  \ number\n        description: lng\n      - name: age\n        type: number\n        description: age\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsections\n      description: Summarize sections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getsections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getunits\n      description: Search units\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getunits\n      with:\n        format: tools.format\n        interval_name: tools.interval_name\n        lith: tools.lith\n      inputParameters:\n      - name: format\n        type: string\n        description: format\n      - name: interval_name\n        type: string\n        description: interval_name\n      - name: lith\n        type: string\n        description: lith\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getfossils\n      description: Search fossils\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getfossils\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstats\n      description: Get database statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getstats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpaleogeography\n      description: Get paleogeography reconstructions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getpaleogeography\n      with:\n        age: tools.age\n      inputParameters:\n      - name: age\n        type: number\n        description: age\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgeologicmapunits\n\
  \      description: Geologic map units\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getgeologicmapunits\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgeologicmappoints\n      description: Geologic map point features\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getgeologicmappoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgeologicmaplegend\n      description: Geologic map legend\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getgeologicmaplegend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmeasurements\n      description: Get measurements\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getmeasurements\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getagemodel\n      description: Get age model\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getagemodel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdefs\n      description: Standard definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getdefs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarto\n      description: Geologic map creation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getcarto\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgrids\n      description: Get grid data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getgrids\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmobile\n      description: Mobile data delivery\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getmobile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmeta\n      description: API metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: macrostrat.getmeta\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/macrostrat/refs/heads/main/capabilities/macrostrat-capability.yaml
tags:
- Macrostrat
- API
tools:
- description: Search columns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcolumns
- description: Summarize sections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsections
- description: Search units
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getunits
- description: Search fossils
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfossils
- description: Get database statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstats
- description: Get paleogeography reconstructions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpaleogeography
- description: Geologic map units
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgeologicmapunits
- description: Geologic map point features
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgeologicmappoints
- description: Geologic map legend
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgeologicmaplegend
- description: Get measurements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeasurements
- description: Get age model
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getagemodel
- description: Standard definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdefs
- description: Geologic map creation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarto
- description: Get grid data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgrids
- description: Mobile data delivery
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmobile
- description: API metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmeta
---
