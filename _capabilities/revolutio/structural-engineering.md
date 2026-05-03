---
api_specs:
- filename: revolutio-hazard-api-openapi.yml
  format: yaml
  label: revolutio
  slug: revolutio
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/revolutio/refs/heads/main/openapi/revolutio-hazard-api-openapi.yml
categories: []
consumed_apis:
- revolutio
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
- construction
- get site wind
- get complete site assessment
- engineering
- get site seismic hazard
- get all hazard parameters (wind, snow, ice, seismic) for a complete site assessment
- wind analysis
- weather
- get site snow
- snow and ice loading parameters for a construction site
- get site assessment
- retrieve seismic hazard class and site classification
- retrieve snow region, elevation class, and ground load for a site
- hazard
- comprehensive multi-hazard site assessment
- hazard assessment
- revolutio
- structural engineering
- wind hazard parameters for a construction site
- get seismic hazard parameters for a site. returns hazard class, site class, and probability factor.
- get a comprehensive multi-hazard site assessment covering wind, snow, ice, and seismic parameters in a single api call. ideal for full structural engineering site evaluations.
- get site wind hazard
- retrieve wind region, terrain category, and design wind speed for a site
- get site seismic
- seismic hazard parameters for a construction site
- get wind hazard parameters for a specific geographic location. returns wind region, terrain category, topographic class, and design wind speed per as/nzs 1170.2 or asce 7.
- get snow and ice loading parameters for a site. returns snow region, elevation class, snow ground load, and ice region classification.
- get site snow hazard
slug: structural-engineering
source_filename: structural-engineering.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Revolutio Structural Engineering Hazard Assessment\"\n  description: >-\n    Workflow capability for comprehensive structural engineering site hazard\n    assessment. Enables engineers and construction software to retrieve wind,\n    snow, ice, and seismic design parameters for any global site using\n    Revolutio's Hazard API, supporting AS/NZS 1170.2, AS 4055, ASCE 7,\n    and other international standards.\n  tags:\n    - Revolutio\n    - Structural Engineering\n    - Wind Analysis\n    - Construction\n    - Hazard Assessment\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REVOLUTIO_API_KEY: REVOLUTIO_API_KEY\n\ncapability:\n  consumes:\n    - import: revolutio\n      location: ./shared/revolutio-hazard-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: revolutio-engineering-api\n      description: \"Unified REST API for structural engineering site\
  \ hazard assessment.\"\n      resources:\n        - path: /v1/sites/wind\n          name: site-wind\n          description: \"Wind hazard parameters for a construction site\"\n          operations:\n            - method: GET\n              name: get-site-wind\n              description: \"Retrieve wind region, terrain category, and design wind speed for a site\"\n              call: \"revolutio.get-wind-hazard\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                h: \"rest.h\"\n                units: \"rest.units\"\n                advancedDetection: \"rest.advanced_detection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sites/snow\n          name: site-snow\n          description: \"Snow and ice loading parameters for a construction site\"\n          operations:\n            - method: GET\n              name: get-site-snow\n     \
  \         description: \"Retrieve snow region, elevation class, and ground load for a site\"\n              call: \"revolutio.get-snow-hazard\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                h: \"rest.h\"\n                units: \"rest.units\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sites/seismic\n          name: site-seismic\n          description: \"Seismic hazard parameters for a construction site\"\n          operations:\n            - method: GET\n              name: get-site-seismic\n              description: \"Retrieve seismic hazard class and site classification\"\n              call: \"revolutio.get-seismic-hazard\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                units: \"rest.units\"\n              outputParameters:\n             \
  \   - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sites/assessment\n          name: site-assessment\n          description: \"Comprehensive multi-hazard site assessment\"\n          operations:\n            - method: GET\n              name: get-site-assessment\n              description: \"Get all hazard parameters (wind, snow, ice, seismic) for a complete site assessment\"\n              call: \"revolutio.get-combined-hazard\"\n              with:\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                h: \"rest.h\"\n                units: \"rest.units\"\n                advancedDetection: \"rest.advanced_detection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: revolutio-engineering-mcp\n      transport: http\n      description: \"MCP server for AI-assisted structural engineering hazard assessment.\"\
  \n      tools:\n        - name: get-site-wind-hazard\n          description: \"Get wind hazard parameters for a specific geographic location. Returns wind region, terrain category, topographic class, and design wind speed per AS/NZS 1170.2 or ASCE 7.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"revolutio.get-wind-hazard\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            h: \"tools.structure_height\"\n            units: \"tools.units\"\n            advancedDetection: \"tools.advanced_detection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-site-snow-hazard\n          description: \"Get snow and ice loading parameters for a site. Returns snow region, elevation class, snow ground load, and ice region classification.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"\
  revolutio.get-snow-hazard\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            h: \"tools.structure_height\"\n            units: \"tools.units\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-site-seismic-hazard\n          description: \"Get seismic hazard parameters for a site. Returns hazard class, site class, and probability factor.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"revolutio.get-seismic-hazard\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            units: \"tools.units\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-complete-site-assessment\n          description: \"Get a comprehensive multi-hazard site assessment covering wind, snow, ice, and seismic parameters in a single\
  \ API call. Ideal for full structural engineering site evaluations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"revolutio.get-combined-hazard\"\n          with:\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            h: \"tools.structure_height\"\n            units: \"tools.units\"\n            advancedDetection: \"tools.advanced_detection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
