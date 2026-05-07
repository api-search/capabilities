---
categories: []
consumed_apis: []
description: The AspenTech Inmation Web API provides HTTP and WebSocket interfaces for external applications to interact with the AspenTech Inmation industrial IoT and time-series data platform. RPC-based REST APIs enable access to process data, system services, and automation functions for manufacturing and energy operations.
layout: capability
name: AspenTech Inmation Web API
operations:
- description: Execute RPC call
  method: POST
  name: executerpccall
  path: /api
- description: Read current process data values
  method: POST
  name: readdataitems
  path: /api/data/read
- description: Write process data values
  method: POST
  name: writedataitems
  path: /api/data/write
- description: Read historical time-series data
  method: POST
  name: readhistoricaldata
  path: /api/data/readhistory
- description: Get system information
  method: GET
  name: getsysteminfo
  path: /api/sys/info
- description: Get configuration item
  method: POST
  name: getconfigurationitem
  path: /api/item/get
personas: []
provider_name: AspenTech
provider_slug: aspentech
search_terms:
- executerpccall
- get system information
- execute rpc call
- getconfigurationitem
- process optimization
- api
- aspentech
- read historical time-series data
- readdataitems
- manufacturing
- read current process data values
- getsysteminfo
- write process data values
- energy
- chemicals
- writedataitems
- industrial iot
- readhistoricaldata
- get configuration item
- time series
slug: aspentech-capability
source_filename: aspentech-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AspenTech Inmation Web API\n  description: The AspenTech Inmation Web API provides HTTP and WebSocket interfaces for external applications to interact\n    with the AspenTech Inmation industrial IoT and time-series data platform. RPC-based REST APIs enable access to process\n    data, system services, and automation functions for manufacturing and energy operations.\n  tags:\n  - Aspentech\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: aspentech\n    baseUri: http://localhost:8002\n    description: AspenTech Inmation Web API HTTP API.\n    authentication:\n      type: basic\n      username: '{{ASPENTECH_USERNAME}}'\n      password: '{{ASPENTECH_PASSWORD}}'\n    resources:\n    - name: api\n      path: /api\n      operations:\n      - name: executerpccall\n        method: POST\n        description: Execute RPC call\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-data-read\n      path: /api/data/read\n      operations:\n      - name: readdataitems\n        method: POST\n        description: Read current process data values\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-data-write\n      path: /api/data/write\n      operations:\n      - name: writedataitems\n        method: POST\n        description: Write process data values\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-data-readhistory\n      path: /api/data/readhistory\n      operations:\n      - name: readhistoricaldata\n        method: POST\n        description: Read historical time-series data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: api-sys-info\n      path: /api/sys/info\n      operations:\n      - name: getsysteminfo\n        method: GET\n        description: Get system information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-item-get\n      path: /api/item/get\n      operations:\n      - name: getconfigurationitem\n        method: POST\n        description: Get configuration item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aspentech-rest\n    description: REST adapter for AspenTech Inmation Web API.\n    resources:\n    - path: /api\n      name: executerpccall\n      operations:\n      - method: POST\n        name: executerpccall\n        description: Execute RPC call\n        call: aspentech.executerpccall\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /api/data/read\n      name: readdataitems\n      operations:\n      - method: POST\n        name: readdataitems\n        description: Read current process data values\n        call: aspentech.readdataitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/data/write\n      name: writedataitems\n      operations:\n      - method: POST\n        name: writedataitems\n        description: Write process data values\n        call: aspentech.writedataitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/data/readhistory\n      name: readhistoricaldata\n      operations:\n      - method: POST\n        name: readhistoricaldata\n        description: Read historical time-series data\n        call: aspentech.readhistoricaldata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/sys/info\n      name: getsysteminfo\n      operations:\n    \
  \  - method: GET\n        name: getsysteminfo\n        description: Get system information\n        call: aspentech.getsysteminfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/item/get\n      name: getconfigurationitem\n      operations:\n      - method: POST\n        name: getconfigurationitem\n        description: Get configuration item\n        call: aspentech.getconfigurationitem\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aspentech-mcp\n    transport: http\n    description: MCP adapter for AspenTech Inmation Web API for AI agent use.\n    tools:\n    - name: executerpccall\n      description: Execute RPC call\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aspentech.executerpccall\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readdataitems\n      description: Read current\
  \ process data values\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aspentech.readdataitems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: writedataitems\n      description: Write process data values\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aspentech.writedataitems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: readhistoricaldata\n      description: Read historical time-series data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aspentech.readhistoricaldata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsysteminfo\n      description: Get system information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aspentech.getsysteminfo\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getconfigurationitem\n      description: Get configuration item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aspentech.getconfigurationitem\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ASPENTECH_USERNAME: ASPENTECH_USERNAME\n    ASPENTECH_PASSWORD: ASPENTECH_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aspentech/refs/heads/main/capabilities/aspentech-capability.yaml
tags:
- Aspentech
- API
tools:
- description: Execute RPC call
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executerpccall
- description: Read current process data values
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: readdataitems
- description: Write process data values
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: writedataitems
- description: Read historical time-series data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: readhistoricaldata
- description: Get system information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsysteminfo
- description: Get configuration item
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getconfigurationitem
---
