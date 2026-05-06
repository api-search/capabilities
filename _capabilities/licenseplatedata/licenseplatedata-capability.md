---
categories: []
consumed_apis: []
description: Developer-first tools that provide access to a library of vehicle information. The API includes Plate to VIN, VIN Decoding, and Vehicle Image services covering passenger cars, ATVs, light and heavy trucks, and trailers from 1980 to current model years.
layout: capability
name: LicensePlateData API
operations:
- description: Convert a license plate to a VIN
  method: GET
  name: platetovin
  path: /plate-to-vin
- description: Decode a VIN
  method: GET
  name: decodevin
  path: /vin/{vin}
- description: Retrieve vehicle images
  method: GET
  name: getvehicleimages
  path: /vehicle-images
personas: []
provider_name: LicensePlateData
provider_slug: licenseplatedata
search_terms:
- decodevin
- decode a vin
- retrieve vehicle images
- vehicles
- plate lookup
- api
- getvehicleimages
- platetovin
- license plates
- vin
- automotive
- vin decoding
- licenseplatedata
- convert a license plate to a vin
slug: licenseplatedata-capability
source_filename: licenseplatedata-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LicensePlateData API\n  description: Developer-first tools that provide access to a library of vehicle information. The API includes Plate to VIN,\n    VIN Decoding, and Vehicle Image services covering passenger cars, ATVs, light and heavy trucks, and trailers from 1980\n    to current model years.\n  tags:\n  - Licenseplatedata\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: licenseplatedata\n    baseUri: https://api.licenseplatedata.com/v1\n    description: LicensePlateData API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{LICENSEPLATEDATA_TOKEN}}'\n    resources:\n    - name: plate-to-vin\n      path: /plate-to-vin\n      operations:\n      - name: platetovin\n        method: GET\n        description: Convert a license plate to a VIN\n        inputParameters:\n        - name: plate\n          in: query\n\
  \          type: string\n          required: true\n          description: License plate number\n        - name: state\n          in: query\n          type: string\n          required: true\n          description: Two-letter US state code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vin-vin\n      path: /vin/{vin}\n      operations:\n      - name: decodevin\n        method: GET\n        description: Decode a VIN\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-images\n      path: /vehicle-images\n      operations:\n      - name: getvehicleimages\n        method: GET\n        description: Retrieve vehicle images\n        inputParameters:\n        - name: vin\n          in: query\n \
  \         type: string\n        - name: year\n          in: query\n          type: integer\n        - name: make\n          in: query\n          type: string\n        - name: model\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: licenseplatedata-rest\n    description: REST adapter for LicensePlateData API.\n    resources:\n    - path: /plate-to-vin\n      name: platetovin\n      operations:\n      - method: GET\n        name: platetovin\n        description: Convert a license plate to a VIN\n        call: licenseplatedata.platetovin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vin/{vin}\n      name: decodevin\n      operations:\n      - method: GET\n        name: decodevin\n        description: Decode a VIN\n        call: licenseplatedata.decodevin\n        with:\n\
  \          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vehicle-images\n      name: getvehicleimages\n      operations:\n      - method: GET\n        name: getvehicleimages\n        description: Retrieve vehicle images\n        call: licenseplatedata.getvehicleimages\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: licenseplatedata-mcp\n    transport: http\n    description: MCP adapter for LicensePlateData API for AI agent use.\n    tools:\n    - name: platetovin\n      description: Convert a license plate to a VIN\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: licenseplatedata.platetovin\n      with:\n        plate: tools.plate\n        state: tools.state\n      inputParameters:\n      - name: plate\n        type: string\n        description: License plate number\n        required: true\n      - name:\
  \ state\n        type: string\n        description: Two-letter US state code\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: decodevin\n      description: Decode a VIN\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: licenseplatedata.decodevin\n      with:\n        vin: tools.vin\n      inputParameters:\n      - name: vin\n        type: string\n        description: vin\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvehicleimages\n      description: Retrieve vehicle images\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: licenseplatedata.getvehicleimages\n      with:\n        vin: tools.vin\n        year: tools.year\n        make: tools.make\n        model: tools.model\n      inputParameters:\n      - name: vin\n        type: string\n        description: vin\n\
  \      - name: year\n        type: integer\n        description: year\n      - name: make\n        type: string\n        description: make\n      - name: model\n        type: string\n        description: model\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LICENSEPLATEDATA_TOKEN: LICENSEPLATEDATA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/licenseplatedata/refs/heads/main/capabilities/licenseplatedata-capability.yaml
tags:
- Licenseplatedata
- API
tools:
- description: Convert a license plate to a VIN
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: platetovin
- description: Decode a VIN
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: decodevin
- description: Retrieve vehicle images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvehicleimages
---
