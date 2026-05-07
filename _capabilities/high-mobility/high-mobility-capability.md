---
categories: []
consumed_apis: []
description: The High Mobility Vehicle API provides standardized access to connected car data across more than 500 models from major automotive OEMs. Endpoints return real-time vehicle telemetry covering location, doors, charging, diagnostics, climate, trips, and other capabilities. Authentication is handled with OAuth 2.0 against the High Mobility platform.
layout: capability
name: High Mobility Vehicle API
operations:
- description: Create OAuth 2.0 access token
  method: POST
  name: createaccesstoken
  path: /v1/access_token
- description: Get vehicle data by VIN
  method: GET
  name: getvehicledata
  path: /v1/vehicle-data/autoapi-13/{vin}
- description: Get vehicle eligibility
  method: GET
  name: getvehicleeligibility
  path: /v1/eligibility/{vin}
- description: List fleet vehicles
  method: GET
  name: listfleetvehicles
  path: /v1/fleet/vehicles
- description: Register vehicle to fleet
  method: POST
  name: addfleetvehicle
  path: /v1/fleet/vehicles
- description: Get fleet vehicle
  method: GET
  name: getfleetvehicle
  path: /v1/fleet/vehicles/{vin}
- description: Remove fleet vehicle
  method: DELETE
  name: removefleetvehicle
  path: /v1/fleet/vehicles/{vin}
personas: []
provider_name: High Mobility
provider_slug: high-mobility
search_terms:
- mobility
- listfleetvehicles
- connected cars
- vehicle data
- api
- create oauth 2.0 access token
- high
- removefleetvehicle
- getfleetvehicle
- get fleet vehicle
- getvehicledata
- addfleetvehicle
- iot
- list fleet vehicles
- get vehicle eligibility
- automotive
- get vehicle data by vin
- getvehicleeligibility
- register vehicle to fleet
- remove fleet vehicle
- createaccesstoken
slug: high-mobility-capability
source_filename: high-mobility-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: High Mobility Vehicle API\n  description: The High Mobility Vehicle API provides standardized access to connected car data across more than 500 models\n    from major automotive OEMs. Endpoints return real-time vehicle telemetry covering location, doors, charging, diagnostics,\n    climate, trips, and other capabilities. Authentication is handled with OAuth 2.0 against the High Mobility platform.\n  tags:\n  - High\n  - Mobility\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: high-mobility\n    baseUri: https://api.high-mobility.com\n    description: High Mobility Vehicle API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HIGH_MOBILITY_TOKEN}}'\n    resources:\n    - name: v1-access-token\n      path: /v1/access_token\n      operations:\n      - name: createaccesstoken\n        method: POST\n        description: Create OAuth 2.0 access token\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-vehicle-data-autoapi-13-vin\n      path: /v1/vehicle-data/autoapi-13/{vin}\n      operations:\n      - name: getvehicledata\n        method: GET\n        description: Get vehicle data by VIN\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: Vehicle Identification Number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-eligibility-vin\n      path: /v1/eligibility/{vin}\n      operations:\n      - name: getvehicleeligibility\n        method: GET\n        description: Get vehicle eligibility\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: v1-fleet-vehicles\n      path: /v1/fleet/vehicles\n      operations:\n      - name: listfleetvehicles\n        method: GET\n        description: List fleet vehicles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addfleetvehicle\n        method: POST\n        description: Register vehicle to fleet\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-fleet-vehicles-vin\n      path: /v1/fleet/vehicles/{vin}\n      operations:\n      - name: getfleetvehicle\n        method: GET\n        description: Get fleet vehicle\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: removefleetvehicle\n        method: DELETE\n        description: Remove fleet vehicle\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: high-mobility-rest\n    description: REST adapter for High Mobility Vehicle API.\n    resources:\n    - path: /v1/access_token\n      name: createaccesstoken\n      operations:\n      - method: POST\n        name: createaccesstoken\n        description: Create OAuth 2.0 access token\n        call: high-mobility.createaccesstoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicle-data/autoapi-13/{vin}\n      name: getvehicledata\n      operations:\n      - method: GET\n        name: getvehicledata\n        description:\
  \ Get vehicle data by VIN\n        call: high-mobility.getvehicledata\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/eligibility/{vin}\n      name: getvehicleeligibility\n      operations:\n      - method: GET\n        name: getvehicleeligibility\n        description: Get vehicle eligibility\n        call: high-mobility.getvehicleeligibility\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fleet/vehicles\n      name: listfleetvehicles\n      operations:\n      - method: GET\n        name: listfleetvehicles\n        description: List fleet vehicles\n        call: high-mobility.listfleetvehicles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fleet/vehicles\n      name: addfleetvehicle\n      operations:\n      - method: POST\n        name: addfleetvehicle\n        description: Register\
  \ vehicle to fleet\n        call: high-mobility.addfleetvehicle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fleet/vehicles/{vin}\n      name: getfleetvehicle\n      operations:\n      - method: GET\n        name: getfleetvehicle\n        description: Get fleet vehicle\n        call: high-mobility.getfleetvehicle\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fleet/vehicles/{vin}\n      name: removefleetvehicle\n      operations:\n      - method: DELETE\n        name: removefleetvehicle\n        description: Remove fleet vehicle\n        call: high-mobility.removefleetvehicle\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: high-mobility-mcp\n    transport: http\n    description: MCP adapter for High Mobility Vehicle API for AI agent use.\n    tools:\n\
  \    - name: createaccesstoken\n      description: Create OAuth 2.0 access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: high-mobility.createaccesstoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvehicledata\n      description: Get vehicle data by VIN\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: high-mobility.getvehicledata\n      with:\n        vin: tools.vin\n      inputParameters:\n      - name: vin\n        type: string\n        description: Vehicle Identification Number.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvehicleeligibility\n      description: Get vehicle eligibility\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: high-mobility.getvehicleeligibility\n      with:\n        vin: tools.vin\n\
  \      inputParameters:\n      - name: vin\n        type: string\n        description: vin\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfleetvehicles\n      description: List fleet vehicles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: high-mobility.listfleetvehicles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addfleetvehicle\n      description: Register vehicle to fleet\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: high-mobility.addfleetvehicle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfleetvehicle\n      description: Get fleet vehicle\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: high-mobility.getfleetvehicle\n      with:\n        vin: tools.vin\n      inputParameters:\n\
  \      - name: vin\n        type: string\n        description: vin\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removefleetvehicle\n      description: Remove fleet vehicle\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: high-mobility.removefleetvehicle\n      with:\n        vin: tools.vin\n      inputParameters:\n      - name: vin\n        type: string\n        description: vin\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HIGH_MOBILITY_TOKEN: HIGH_MOBILITY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/high-mobility/refs/heads/main/capabilities/high-mobility-capability.yaml
tags:
- High
- Mobility
- API
tools:
- description: Create OAuth 2.0 access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createaccesstoken
- description: Get vehicle data by VIN
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvehicledata
- description: Get vehicle eligibility
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvehicleeligibility
- description: List fleet vehicles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfleetvehicles
- description: Register vehicle to fleet
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addfleetvehicle
- description: Get fleet vehicle
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfleetvehicle
- description: Remove fleet vehicle
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removefleetvehicle
---
