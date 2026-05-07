---
categories: []
consumed_apis: []
description: The Chicago Transit Authority Bus Tracker API provides real-time bus arrival predictions, vehicle locations, route patterns, route lists, and stop directories for the CTA bus network. Access requires an API key issued by the CTA Developer Center.
layout: capability
name: CTA Bus Tracker API
operations:
- description: Get System Time
  method: GET
  name: gettime
  path: /gettime
- description: Get Routes
  method: GET
  name: getroutes
  path: /getroutes
- description: Get Directions
  method: GET
  name: getdirections
  path: /getdirections
- description: Get Stops
  method: GET
  name: getstops
  path: /getstops
- description: Get Patterns
  method: GET
  name: getpatterns
  path: /getpatterns
- description: Get Vehicles
  method: GET
  name: getvehicles
  path: /getvehicles
- description: Get Predictions
  method: GET
  name: getpredictions
  path: /getpredictions
- description: Get Service Bulletins
  method: GET
  name: getservicebulletins
  path: /getservicebulletins
personas: []
provider_name: Chicago Transit Authority
provider_slug: chicago-transit-authority
search_terms:
- gettime
- api
- get directions
- getvehicles
- getservicebulletins
- gtfs
- cta
- getpredictions
- get system time
- bus
- chicago
- get service bulletins
- get predictions
- get stops
- train tracker
- get vehicles
- customer alerts
- train
- transportation
- getstops
- get patterns
- bus tracker
- authority
- l train
- public transit
- getroutes
- getdirections
- transit
- getpatterns
- real-time
- open data
- get routes
slug: chicago-transit-authority-capability
source_filename: chicago-transit-authority-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CTA Bus Tracker API\n  description: The Chicago Transit Authority Bus Tracker API provides real-time bus arrival predictions, vehicle locations,\n    route patterns, route lists, and stop directories for the CTA bus network. Access requires an API key issued by the CTA\n    Developer Center.\n  tags:\n  - Chicago\n  - Transit\n  - Authority\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: chicago-transit-authority\n    baseUri: http://www.ctabustracker.com/bustime/api/v2\n    description: CTA Bus Tracker API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{CHICAGO_TRANSIT_AUTHORITY_TOKEN}}'\n    resources:\n    - name: gettime\n      path: /gettime\n      operations:\n      - name: gettime\n        method: GET\n        description: Get System Time\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: getroutes\n      path: /getroutes\n      operations:\n      - name: getroutes\n        method: GET\n        description: Get Routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getdirections\n      path: /getdirections\n      operations:\n      - name: getdirections\n        method: GET\n        description: Get Directions\n        inputParameters:\n        - name: rt\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getstops\n      path: /getstops\n      operations:\n      - name: getstops\n        method: GET\n        description: Get Stops\n        inputParameters:\n        - name: rt\n          in: query\n          type: string\n          required: true\n   \
  \     - name: dir\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getpatterns\n      path: /getpatterns\n      operations:\n      - name: getpatterns\n        method: GET\n        description: Get Patterns\n        inputParameters:\n        - name: rt\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getvehicles\n      path: /getvehicles\n      operations:\n      - name: getvehicles\n        method: GET\n        description: Get Vehicles\n        inputParameters:\n        - name: vid\n          in: query\n          type: string\n          description: Comma-separated vehicle IDs.\n        - name: rt\n          in: query\n          type: string\n          description:\
  \ Comma-separated route designators.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getpredictions\n      path: /getpredictions\n      operations:\n      - name: getpredictions\n        method: GET\n        description: Get Predictions\n        inputParameters:\n        - name: stpid\n          in: query\n          type: string\n          description: Comma-separated stop IDs.\n        - name: rt\n          in: query\n          type: string\n          description: Comma-separated route designators.\n        - name: vid\n          in: query\n          type: string\n          description: Comma-separated vehicle IDs.\n        - name: top\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getservicebulletins\n      path: /getservicebulletins\n      operations:\n  \
  \    - name: getservicebulletins\n        method: GET\n        description: Get Service Bulletins\n        inputParameters:\n        - name: rt\n          in: query\n          type: string\n        - name: stpid\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: chicago-transit-authority-rest\n    description: REST adapter for CTA Bus Tracker API.\n    resources:\n    - path: /gettime\n      name: gettime\n      operations:\n      - method: GET\n        name: gettime\n        description: Get System Time\n        call: chicago-transit-authority.gettime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getroutes\n      name: getroutes\n      operations:\n      - method: GET\n        name: getroutes\n        description: Get Routes\n        call: chicago-transit-authority.getroutes\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getdirections\n      name: getdirections\n      operations:\n      - method: GET\n        name: getdirections\n        description: Get Directions\n        call: chicago-transit-authority.getdirections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getstops\n      name: getstops\n      operations:\n      - method: GET\n        name: getstops\n        description: Get Stops\n        call: chicago-transit-authority.getstops\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getpatterns\n      name: getpatterns\n      operations:\n      - method: GET\n        name: getpatterns\n        description: Get Patterns\n        call: chicago-transit-authority.getpatterns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getvehicles\n      name: getvehicles\n      operations:\n      - method: GET\n\
  \        name: getvehicles\n        description: Get Vehicles\n        call: chicago-transit-authority.getvehicles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getpredictions\n      name: getpredictions\n      operations:\n      - method: GET\n        name: getpredictions\n        description: Get Predictions\n        call: chicago-transit-authority.getpredictions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /getservicebulletins\n      name: getservicebulletins\n      operations:\n      - method: GET\n        name: getservicebulletins\n        description: Get Service Bulletins\n        call: chicago-transit-authority.getservicebulletins\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: chicago-transit-authority-mcp\n    transport: http\n    description: MCP adapter for CTA Bus Tracker API for AI agent use.\n    tools:\n    - name:\
  \ gettime\n      description: Get System Time\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chicago-transit-authority.gettime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getroutes\n      description: Get Routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chicago-transit-authority.getroutes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdirections\n      description: Get Directions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chicago-transit-authority.getdirections\n      with:\n        rt: tools.rt\n      inputParameters:\n      - name: rt\n        type: string\n        description: rt\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstops\n      description: Get Stops\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chicago-transit-authority.getstops\n      with:\n        rt: tools.rt\n        dir: tools.dir\n      inputParameters:\n      - name: rt\n        type: string\n        description: rt\n        required: true\n      - name: dir\n        type: string\n        description: dir\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatterns\n      description: Get Patterns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chicago-transit-authority.getpatterns\n      with:\n        rt: tools.rt\n      inputParameters:\n      - name: rt\n        type: string\n        description: rt\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvehicles\n      description: Get Vehicles\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: chicago-transit-authority.getvehicles\n      with:\n        vid: tools.vid\n        rt: tools.rt\n      inputParameters:\n      - name: vid\n        type: string\n        description: Comma-separated vehicle IDs.\n      - name: rt\n        type: string\n        description: Comma-separated route designators.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpredictions\n      description: Get Predictions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chicago-transit-authority.getpredictions\n      with:\n        stpid: tools.stpid\n        rt: tools.rt\n        vid: tools.vid\n        top: tools.top\n      inputParameters:\n      - name: stpid\n        type: string\n        description: Comma-separated stop IDs.\n      - name: rt\n        type: string\n        description: Comma-separated route designators.\n      - name: vid\n        type: string\n       \
  \ description: Comma-separated vehicle IDs.\n      - name: top\n        type: integer\n        description: top\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservicebulletins\n      description: Get Service Bulletins\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chicago-transit-authority.getservicebulletins\n      with:\n        rt: tools.rt\n        stpid: tools.stpid\n      inputParameters:\n      - name: rt\n        type: string\n        description: rt\n      - name: stpid\n        type: string\n        description: stpid\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHICAGO_TRANSIT_AUTHORITY_TOKEN: CHICAGO_TRANSIT_AUTHORITY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/chicago-transit-authority/refs/heads/main/capabilities/chicago-transit-authority-capability.yaml
tags:
- Chicago
- Transit
- Authority
- API
tools:
- description: Get System Time
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettime
- description: Get Routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroutes
- description: Get Directions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdirections
- description: Get Stops
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstops
- description: Get Patterns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatterns
- description: Get Vehicles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvehicles
- description: Get Predictions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpredictions
- description: Get Service Bulletins
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservicebulletins
---
