---
categories: []
consumed_apis: []
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
- get active correction service and accuracy level
- gnss position stream initialization
- get connected trimble gnss receiver model, serial number, and firmware version
- list available catalyst positioning accuracy licenses
- get receiver info
- gps
- navigation
- construction
- configure rtx, rtk, sbas, or ntrip corrections
- activate a trimble catalyst on demand license for enhanced positioning accuracy
- get tmm version and websocket port information
- gnss receiver hardware details
- activate catalyst on demand license for enhanced accuracy
- positioning
- current receiver status
- geospatial
- get trimble mobile manager system information including websocket ports
- initiate real-time gnss position streaming
- get receiver status
- configure gnss correction source (rtx, rtk, sbas, or ntrip)
- get receiver connection and signal status
- gnss correction service status
- get connected receiver model and firmware version
- gnss
- configure correction sources
- catalyst accuracy licenses
- surveying
- start real-time gnss position streaming, returns websocket port to connect to
- list available trimble catalyst positioning accuracy licenses
- precision agriculture
- tmm system information
- start position stream
- get tmm info
- get corrections status
- get catalyst licenses
- configure corrections
- check active gnss correction service (rtx, rtk, sbas) and current accuracy
- activate catalyst license
- check current gnss receiver connection status and signal strength
- trimble navigation
slug: gnss-positioning
source_filename: gnss-positioning.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trimble Navigation GNSS Positioning\n  description: Unified GNSS positioning capability combining Trimble Mobile Manager receiver integration, real-time position\n    streaming, correction service management, and Catalyst license activation. Powers high-accuracy field data collection\n    apps for surveying, construction, and precision agriculture.\n  tags:\n  - Trimble Navigation\n  - GPS\n  - GNSS\n  - Positioning\n  - Navigation\n  - Surveying\n  - Precision Agriculture\n  - Construction\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TMM_APP_ID: TMM_APP_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: trimble-tmm\n    baseUri: http://localhost:8080\n    description: Trimble Mobile Manager local REST API\n    authentication:\n      type: basic\n      username: '{{TMM_APP_ID}}'\n      password: '{{TMM_ACCESS_CODE}}'\n    resources:\n    - name: system\n      path: /api/v1/tmmInfo\n\
  \      description: TMM system information\n      operations:\n      - name: get-tmm-info\n        method: GET\n        description: Get TMM version, API port, and WebSocket ports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: positioning\n      path: /api/v1/positionStream\n      description: GNSS position streaming\n      operations:\n      - name: start-position-stream\n        method: GET\n        description: Initiate GNSS position streaming, returns WebSocket port\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Position format (locationV1 or locationV2)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: receiver\n      path: /api/v1/receiver\n      description: GNSS receiver management\n      operations:\n\
  \      - name: get-receiver-info\n        method: GET\n        description: Get connected receiver model and firmware details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-receiver-status\n        method: GET\n        description: Get current receiver status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: corrections\n      path: /api/v1/corrections\n      description: GNSS correction service management\n      operations:\n      - name: get-corrections-status\n        method: GET\n        description: Get active correction service status and accuracy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: configure-corrections\n        method: POST\n        description: Configure correction source (RTX, RTK, SBAS,\
  \ NTRIP)\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            ntripHost: '{{tools.ntripHost}}'\n            ntripMountpoint: '{{tools.ntripMountpoint}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalyst\n      path: /api/v1/catalyst\n      description: Trimble Catalyst license management\n      operations:\n      - name: get-catalyst-licenses\n        method: GET\n        description: Get available Catalyst accuracy licenses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: activate-catalyst-license\n        method: POST\n        description: Activate a Catalyst On Demand license\n        body:\n          type: json\n          data:\n            licenseId: '{{tools.licenseId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gnss-positioning-api\n    description: Unified REST API for Trimble GNSS positioning and receiver management.\n    resources:\n    - path: /v1/system/info\n      name: system-info\n      description: TMM system information\n      operations:\n      - method: GET\n        name: get-tmm-info\n        description: Get TMM version and WebSocket port information\n        call: trimble-tmm.get-tmm-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/position/stream\n      name: position-stream\n      description: GNSS position stream initialization\n      operations:\n      - method: GET\n        name: start-position-stream\n        description: Initiate real-time GNSS position streaming\n        call: trimble-tmm.start-position-stream\n        with:\n          format: rest.format\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /v1/receiver/info\n      name: receiver-info\n      description: GNSS receiver hardware details\n      operations:\n      - method: GET\n        name: get-receiver-info\n        description: Get connected receiver model and firmware version\n        call: trimble-tmm.get-receiver-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/receiver/status\n      name: receiver-status\n      description: Current receiver status\n      operations:\n      - method: GET\n        name: get-receiver-status\n        description: Get receiver connection and signal status\n        call: trimble-tmm.get-receiver-status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/corrections/status\n      name: corrections-status\n      description: GNSS correction service status\n      operations:\n      - method: GET\n        name: get-corrections-status\n        description: Get active correction service\
  \ and accuracy level\n        call: trimble-tmm.get-corrections-status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/corrections/configure\n      name: corrections-config\n      description: Configure correction sources\n      operations:\n      - method: POST\n        name: configure-corrections\n        description: Configure RTX, RTK, SBAS, or NTRIP corrections\n        call: trimble-tmm.configure-corrections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalyst/licenses\n      name: catalyst-licenses\n      description: Catalyst accuracy licenses\n      operations:\n      - method: GET\n        name: get-catalyst-licenses\n        description: List available Catalyst positioning accuracy licenses\n        call: trimble-tmm.get-catalyst-licenses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalyst/licenses/activate\n      name: catalyst-activate\n\
  \      description: Activate Catalyst license\n      operations:\n      - method: POST\n        name: activate-catalyst-license\n        description: Activate Catalyst On Demand license for enhanced accuracy\n        call: trimble-tmm.activate-catalyst-license\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gnss-positioning-mcp\n    transport: http\n    description: MCP server for AI-assisted GNSS receiver management and positioning.\n    tools:\n    - name: get-tmm-info\n      description: Get Trimble Mobile Manager system information including WebSocket ports\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-tmm.get-tmm-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-position-stream\n      description: Start real-time GNSS position streaming, returns WebSocket port to connect to\n      hints:\n        readOnly: false\n        openWorld:\
  \ false\n      call: trimble-tmm.start-position-stream\n      with:\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-receiver-info\n      description: Get connected Trimble GNSS receiver model, serial number, and firmware version\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-tmm.get-receiver-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-receiver-status\n      description: Check current GNSS receiver connection status and signal strength\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-tmm.get-receiver-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-corrections-status\n      description: Check active GNSS correction service (RTX, RTK, SBAS) and current accuracy\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-tmm.get-corrections-status\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: configure-corrections\n      description: Configure GNSS correction source (RTX, RTK, SBAS, or NTRIP)\n      hints:\n        readOnly: false\n        idempotent: true\n      call: trimble-tmm.configure-corrections\n      with:\n        type: tools.type\n        ntripHost: tools.ntripHost\n        ntripMountpoint: tools.ntripMountpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-catalyst-licenses\n      description: List available Trimble Catalyst positioning accuracy licenses\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-tmm.get-catalyst-licenses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activate-catalyst-license\n      description: Activate a Trimble Catalyst On Demand license for enhanced positioning accuracy\n      hints:\n        readOnly: false\n        openWorld: false\n      call: trimble-tmm.activate-catalyst-license\n\
  \      with:\n        licenseId: tools.licenseId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
