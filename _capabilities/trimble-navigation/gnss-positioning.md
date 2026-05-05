---
api_specs:
- filename: trimble-mobile-manager-openapi.yml
  format: yaml
  label: trimble-tmm
  slug: trimble-tmm
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/trimble-navigation/refs/heads/main/openapi/trimble-mobile-manager-openapi.yml
categories: []
consumed_apis:
- trimble-tmm
description: Unified GNSS positioning capability combining Trimble Mobile Manager receiver integration, real-time position streaming, correction service management, and Catalyst license activation. Powers high-accuracy field data collection apps for surveying, construction, and precision agriculture.
layout: capability
name: Trimble Navigation GNSS Positioning
operations:
- description: Get TMM version and WebSocket port information
  method: GET
  name: get-tmm-info
  path: /v1/system/info
- description: Initiate real-time GNSS position streaming
  method: GET
  name: start-position-stream
  path: /v1/position/stream
- description: Get connected receiver model and firmware version
  method: GET
  name: get-receiver-info
  path: /v1/receiver/info
- description: Get receiver connection and signal status
  method: GET
  name: get-receiver-status
  path: /v1/receiver/status
- description: Get active correction service and accuracy level
  method: GET
  name: get-corrections-status
  path: /v1/corrections/status
- description: Configure RTX, RTK, SBAS, or NTRIP corrections
  method: POST
  name: configure-corrections
  path: /v1/corrections/configure
- description: List available Catalyst positioning accuracy licenses
  method: GET
  name: get-catalyst-licenses
  path: /v1/catalyst/licenses
- description: Activate Catalyst On Demand license for enhanced accuracy
  method: POST
  name: activate-catalyst-license
  path: /v1/catalyst/licenses/activate
personas: []
provider_name: Trimble Navigation
provider_slug: trimble-navigation
search_terms:
- gps
- positioning
- get receiver status
- get receiver connection and signal status
- configure rtx, rtk, sbas, or ntrip corrections
- geospatial
- activate a trimble catalyst on demand license for enhanced positioning accuracy
- check current gnss receiver connection status and signal strength
- construction
- get receiver info
- initiate real-time gnss position streaming
- check active gnss correction service (rtx, rtk, sbas) and current accuracy
- precision agriculture
- tmm system information
- gnss correction service status
- get tmm version and websocket port information
- gnss position stream initialization
- start real-time gnss position streaming, returns websocket port to connect to
- activate catalyst on demand license for enhanced accuracy
- get active correction service and accuracy level
- current receiver status
- get catalyst licenses
- configure gnss correction source (rtx, rtk, sbas, or ntrip)
- activate catalyst license
- surveying
- catalyst accuracy licenses
- list available catalyst positioning accuracy licenses
- get tmm info
- gnss
- gnss receiver hardware details
- get trimble mobile manager system information including websocket ports
- get connected trimble gnss receiver model, serial number, and firmware version
- navigation
- configure correction sources
- get corrections status
- configure corrections
- trimble navigation
- list available trimble catalyst positioning accuracy licenses
- get connected receiver model and firmware version
- start position stream
slug: gnss-positioning
source_filename: gnss-positioning.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trimble Navigation GNSS Positioning\"\n  description: >-\n    Unified GNSS positioning capability combining Trimble Mobile Manager receiver\n    integration, real-time position streaming, correction service management, and\n    Catalyst license activation. Powers high-accuracy field data collection apps\n    for surveying, construction, and precision agriculture.\n  tags:\n    - Trimble Navigation\n    - GPS\n    - GNSS\n    - Positioning\n    - Navigation\n    - Surveying\n    - Precision Agriculture\n    - Construction\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TMM_APP_ID: TMM_APP_ID\n\ncapability:\n  consumes:\n    - import: trimble-tmm\n      location: ./shared/trimble-mobile-manager.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: gnss-positioning-api\n      description: \"Unified REST API for Trimble GNSS positioning and receiver management.\"\
  \n      resources:\n        - path: /v1/system/info\n          name: system-info\n          description: TMM system information\n          operations:\n            - method: GET\n              name: get-tmm-info\n              description: Get TMM version and WebSocket port information\n              call: \"trimble-tmm.get-tmm-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/position/stream\n          name: position-stream\n          description: GNSS position stream initialization\n          operations:\n            - method: GET\n              name: start-position-stream\n              description: Initiate real-time GNSS position streaming\n              call: \"trimble-tmm.start-position-stream\"\n              with:\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/receiver/info\n       \
  \   name: receiver-info\n          description: GNSS receiver hardware details\n          operations:\n            - method: GET\n              name: get-receiver-info\n              description: Get connected receiver model and firmware version\n              call: \"trimble-tmm.get-receiver-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/receiver/status\n          name: receiver-status\n          description: Current receiver status\n          operations:\n            - method: GET\n              name: get-receiver-status\n              description: Get receiver connection and signal status\n              call: \"trimble-tmm.get-receiver-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/corrections/status\n          name: corrections-status\n          description: GNSS correction service status\n          operations:\n   \
  \         - method: GET\n              name: get-corrections-status\n              description: Get active correction service and accuracy level\n              call: \"trimble-tmm.get-corrections-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/corrections/configure\n          name: corrections-config\n          description: Configure correction sources\n          operations:\n            - method: POST\n              name: configure-corrections\n              description: Configure RTX, RTK, SBAS, or NTRIP corrections\n              call: \"trimble-tmm.configure-corrections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalyst/licenses\n          name: catalyst-licenses\n          description: Catalyst accuracy licenses\n          operations:\n            - method: GET\n              name: get-catalyst-licenses\n           \
  \   description: List available Catalyst positioning accuracy licenses\n              call: \"trimble-tmm.get-catalyst-licenses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalyst/licenses/activate\n          name: catalyst-activate\n          description: Activate Catalyst license\n          operations:\n            - method: POST\n              name: activate-catalyst-license\n              description: Activate Catalyst On Demand license for enhanced accuracy\n              call: \"trimble-tmm.activate-catalyst-license\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: gnss-positioning-mcp\n      transport: http\n      description: \"MCP server for AI-assisted GNSS receiver management and positioning.\"\n      tools:\n        - name: get-tmm-info\n          description: Get Trimble Mobile Manager system\
  \ information including WebSocket ports\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-tmm.get-tmm-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-position-stream\n          description: Start real-time GNSS position streaming, returns WebSocket port to connect to\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trimble-tmm.start-position-stream\"\n          with:\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-receiver-info\n          description: Get connected Trimble GNSS receiver model, serial number, and firmware version\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-tmm.get-receiver-info\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n\n        - name: get-receiver-status\n          description: Check current GNSS receiver connection status and signal strength\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-tmm.get-receiver-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-corrections-status\n          description: Check active GNSS correction service (RTX, RTK, SBAS) and current accuracy\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-tmm.get-corrections-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: configure-corrections\n          description: Configure GNSS correction source (RTX, RTK, SBAS, or NTRIP)\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"trimble-tmm.configure-corrections\"\n         \
  \ with:\n            type: \"tools.type\"\n            ntripHost: \"tools.ntripHost\"\n            ntripMountpoint: \"tools.ntripMountpoint\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-catalyst-licenses\n          description: List available Trimble Catalyst positioning accuracy licenses\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-tmm.get-catalyst-licenses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: activate-catalyst-license\n          description: Activate a Trimble Catalyst On Demand license for enhanced positioning accuracy\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trimble-tmm.activate-catalyst-license\"\n          with:\n            licenseId: \"tools.licenseId\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trimble-navigation/refs/heads/main/capabilities/gnss-positioning.yaml
tags:
- Trimble Navigation
- GPS
- GNSS
- Positioning
- Navigation
- Surveying
- Precision Agriculture
- Construction
tools:
- description: Get Trimble Mobile Manager system information including WebSocket ports
  hints:
    openWorld: false
    readOnly: true
  name: get-tmm-info
- description: Start real-time GNSS position streaming, returns WebSocket port to connect to
  hints:
    openWorld: false
    readOnly: false
  name: start-position-stream
- description: Get connected Trimble GNSS receiver model, serial number, and firmware version
  hints:
    openWorld: false
    readOnly: true
  name: get-receiver-info
- description: Check current GNSS receiver connection status and signal strength
  hints:
    openWorld: false
    readOnly: true
  name: get-receiver-status
- description: Check active GNSS correction service (RTX, RTK, SBAS) and current accuracy
  hints:
    openWorld: false
    readOnly: true
  name: get-corrections-status
- description: Configure GNSS correction source (RTX, RTK, SBAS, or NTRIP)
  hints:
    idempotent: true
    readOnly: false
  name: configure-corrections
- description: List available Trimble Catalyst positioning accuracy licenses
  hints:
    openWorld: false
    readOnly: true
  name: get-catalyst-licenses
- description: Activate a Trimble Catalyst On Demand license for enhanced positioning accuracy
  hints:
    openWorld: false
    readOnly: false
  name: activate-catalyst-license
---
