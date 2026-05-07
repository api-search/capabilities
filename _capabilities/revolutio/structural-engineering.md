---
categories: []
consumed_apis: []
description: Workflow capability for comprehensive structural engineering site hazard assessment. Enables engineers and construction software to retrieve wind, snow, ice, and seismic design parameters for any global site using Revolutio's Hazard API, supporting AS/NZS 1170.2, AS 4055, ASCE 7, and other international standards.
layout: capability
name: Revolutio Structural Engineering Hazard Assessment
operations:
- description: Retrieve wind region, terrain category, and design wind speed for a site
  method: GET
  name: get-site-wind
  path: /v1/sites/wind
- description: Retrieve snow region, elevation class, and ground load for a site
  method: GET
  name: get-site-snow
  path: /v1/sites/snow
- description: Retrieve seismic hazard class and site classification
  method: GET
  name: get-site-seismic
  path: /v1/sites/seismic
- description: Get all hazard parameters (wind, snow, ice, seismic) for a complete site assessment
  method: GET
  name: get-site-assessment
  path: /v1/sites/assessment
personas: []
provider_name: Revolutio
provider_slug: revolutio
search_terms:
- engineering
- get site wind
- wind hazard parameters for a construction site
- get site snow hazard
- get complete site assessment
- seismic hazard parameters for a construction site
- construction
- retrieve snow region, elevation class, and ground load for a site
- get seismic hazard parameters for a site. returns hazard class, site class, and probability factor.
- snow and ice loading parameters for a construction site
- revolutio
- hazard
- comprehensive multi-hazard site assessment
- get site wind hazard
- structural engineering
- get site seismic hazard
- wind analysis
- get site seismic
- retrieve wind region, terrain category, and design wind speed for a site
- get site assessment
- get snow and ice loading parameters for a site. returns snow region, elevation class, snow ground load, and ice region classification.
- hazard assessment
- retrieve seismic hazard class and site classification
- get a comprehensive multi-hazard site assessment covering wind, snow, ice, and seismic parameters in a single api call. ideal for full structural engineering site evaluations.
- get site snow
- weather
- get wind hazard parameters for a specific geographic location. returns wind region, terrain category, topographic class, and design wind speed per as/nzs 1170.2 or asce 7.
- get all hazard parameters (wind, snow, ice, seismic) for a complete site assessment
slug: structural-engineering
source_filename: structural-engineering.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Revolutio Structural Engineering Hazard Assessment\n  description: Workflow capability for comprehensive structural engineering site hazard assessment. Enables engineers and\n    construction software to retrieve wind, snow, ice, and seismic design parameters for any global site using Revolutio's\n    Hazard API, supporting AS/NZS 1170.2, AS 4055, ASCE 7, and other international standards.\n  tags:\n  - Revolutio\n  - Structural Engineering\n  - Wind Analysis\n  - Construction\n  - Hazard Assessment\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REVOLUTIO_API_KEY: REVOLUTIO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: revolutio\n    baseUri: https://api.revolutio.com.au\n    description: Revolutio Hazard API for site-specific wind, snow, ice, and seismic analysis\n    authentication:\n      type: apikey\n      key: apiKey\n      value: '{{REVOLUTIO_API_KEY}}'\n      placement:\
  \ query\n    resources:\n    - name: wind-analysis\n      path: /asnzs1170/wind\n      description: Wind hazard analysis per AS/NZS 1170.2 and ASCE 7\n      operations:\n      - name: get-wind-hazard\n        method: GET\n        description: Get site-specific wind hazard parameters\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Site latitude in decimal degrees\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Site longitude in decimal degrees\n        - name: h\n          in: query\n          type: number\n          required: false\n          description: Structure height in metres\n        - name: units\n          in: query\n          type: string\n          required: false\n          description: 'Output units: metric or imperial'\n        - name: advancedDetection\n          in: query\n          type: boolean\n \
  \         required: false\n          description: Enable ML terrain detection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: snow-analysis\n      path: /asnzs1170/snow\n      description: Snow and ice loading analysis\n      operations:\n      - name: get-snow-hazard\n        method: GET\n        description: Get site-specific snow and ice loading parameters\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Site latitude in decimal degrees\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Site longitude in decimal degrees\n        - name: h\n          in: query\n          type: number\n          required: false\n          description: Structure height in metres\n        - name: units\n          in: query\n          type: string\n\
  \          required: false\n          description: 'Output units: metric or imperial'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: seismic-analysis\n      path: /asnzs1170/seismic\n      description: Seismic hazard analysis\n      operations:\n      - name: get-seismic-hazard\n        method: GET\n        description: Get site-specific seismic hazard parameters\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Site latitude in decimal degrees\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Site longitude in decimal degrees\n        - name: units\n          in: query\n          type: string\n          required: false\n          description: 'Output units: metric or imperial'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: combined-hazard\n      path: /asnzs1170/combined\n      description: Combined multi-hazard analysis\n      operations:\n      - name: get-combined-hazard\n        method: GET\n        description: Get all hazard parameters (wind, snow, ice, seismic) for a site\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Site latitude in decimal degrees\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Site longitude in decimal degrees\n        - name: h\n          in: query\n          type: number\n          required: false\n          description: Structure height in metres\n        - name: units\n          in: query\n          type: string\n          required: false\n          description: 'Output units: metric or imperial'\n        - name: advancedDetection\n\
  \          in: query\n          type: boolean\n          required: false\n          description: Enable ML terrain detection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: revolutio-engineering-api\n    description: Unified REST API for structural engineering site hazard assessment.\n    resources:\n    - path: /v1/sites/wind\n      name: site-wind\n      description: Wind hazard parameters for a construction site\n      operations:\n      - method: GET\n        name: get-site-wind\n        description: Retrieve wind region, terrain category, and design wind speed for a site\n        call: revolutio.get-wind-hazard\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n          h: rest.h\n          units: rest.units\n          advancedDetection: rest.advanced_detection\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/sites/snow\n      name: site-snow\n      description: Snow and ice loading parameters for a construction site\n      operations:\n      - method: GET\n        name: get-site-snow\n        description: Retrieve snow region, elevation class, and ground load for a site\n        call: revolutio.get-snow-hazard\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n          h: rest.h\n          units: rest.units\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sites/seismic\n      name: site-seismic\n      description: Seismic hazard parameters for a construction site\n      operations:\n      - method: GET\n        name: get-site-seismic\n        description: Retrieve seismic hazard class and site classification\n        call: revolutio.get-seismic-hazard\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n          units: rest.units\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sites/assessment\n      name: site-assessment\n      description: Comprehensive multi-hazard site assessment\n      operations:\n      - method: GET\n        name: get-site-assessment\n        description: Get all hazard parameters (wind, snow, ice, seismic) for a complete site assessment\n        call: revolutio.get-combined-hazard\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n          h: rest.h\n          units: rest.units\n          advancedDetection: rest.advanced_detection\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: revolutio-engineering-mcp\n    transport: http\n    description: MCP server for AI-assisted structural engineering hazard assessment.\n    tools:\n    - name: get-site-wind-hazard\n      description: Get wind hazard parameters for a specific geographic location. Returns\
  \ wind region, terrain category, topographic\n        class, and design wind speed per AS/NZS 1170.2 or ASCE 7.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: revolutio.get-wind-hazard\n      with:\n        latitude: tools.latitude\n        longitude: tools.longitude\n        h: tools.structure_height\n        units: tools.units\n        advancedDetection: tools.advanced_detection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-site-snow-hazard\n      description: Get snow and ice loading parameters for a site. Returns snow region, elevation class, snow ground load,\n        and ice region classification.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: revolutio.get-snow-hazard\n      with:\n        latitude: tools.latitude\n        longitude: tools.longitude\n        h: tools.structure_height\n        units: tools.units\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: get-site-seismic-hazard\n      description: Get seismic hazard parameters for a site. Returns hazard class, site class, and probability factor.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: revolutio.get-seismic-hazard\n      with:\n        latitude: tools.latitude\n        longitude: tools.longitude\n        units: tools.units\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-complete-site-assessment\n      description: Get a comprehensive multi-hazard site assessment covering wind, snow, ice, and seismic parameters in a\n        single API call. Ideal for full structural engineering site evaluations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: revolutio.get-combined-hazard\n      with:\n        latitude: tools.latitude\n        longitude: tools.longitude\n        h: tools.structure_height\n        units: tools.units\n        advancedDetection: tools.advanced_detection\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/revolutio/refs/heads/main/capabilities/structural-engineering.yaml
tags:
- Revolutio
- Structural Engineering
- Wind Analysis
- Construction
- Hazard Assessment
tools:
- description: Get wind hazard parameters for a specific geographic location. Returns wind region, terrain category, topographic class, and design wind speed per AS/NZS 1170.2 or ASCE 7.
  hints:
    openWorld: true
    readOnly: true
  name: get-site-wind-hazard
- description: Get snow and ice loading parameters for a site. Returns snow region, elevation class, snow ground load, and ice region classification.
  hints:
    openWorld: true
    readOnly: true
  name: get-site-snow-hazard
- description: Get seismic hazard parameters for a site. Returns hazard class, site class, and probability factor.
  hints:
    openWorld: true
    readOnly: true
  name: get-site-seismic-hazard
- description: Get a comprehensive multi-hazard site assessment covering wind, snow, ice, and seismic parameters in a single API call. Ideal for full structural engineering site evaluations.
  hints:
    openWorld: true
    readOnly: true
  name: get-complete-site-assessment
---
