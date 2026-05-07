---
categories: []
consumed_apis: []
description: Parcel-level zoning data for commercial real estate, builder, and developer markets. Returns zoning districts, allowed uses, setback requirements, floor area ratio (FAR), building height limits, and other zoning attributes for a given parcel or location.
layout: capability
name: LightBox Zoning API
operations:
- description: Get zoning by parcel ID
  method: GET
  name: getzoningbyparcel
  path: /zoning/us/parcel/{parcelId}
- description: Get zoning by address
  method: GET
  name: getzoningbyaddress
  path: /zoning/us/address
- description: Get zoning by geometry
  method: POST
  name: getzoningbygeometry
  path: /zoning/us/geometry
personas: []
provider_name: LightBox Zoning API
provider_slug: lightbox-zoning-api
search_terms:
- getzoningbygeometry
- getzoningbyparcel
- get zoning by address
- land use
- real estate
- getzoningbyaddress
- property
- get zoning by geometry
- get zoning by parcel id
- api
- geospatial
- zoning
- parcels
- lightbox
- cre
slug: lightbox-zoning-api-capability
source_filename: lightbox-zoning-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LightBox Zoning API\n  description: Parcel-level zoning data for commercial real estate, builder, and developer markets. Returns zoning districts,\n    allowed uses, setback requirements, floor area ratio (FAR), building height limits, and other zoning attributes for a\n    given parcel or location.\n  tags:\n  - Lightbox\n  - Zoning\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lightbox-zoning-api\n    baseUri: https://api.lightboxre.com/v1\n    description: LightBox Zoning API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{LIGHTBOX_ZONING_API_TOKEN}}'\n    resources:\n    - name: zoning-us-parcel-parcelid\n      path: /zoning/us/parcel/{parcelId}\n      operations:\n      - name: getzoningbyparcel\n        method: GET\n        description: Get zoning by parcel ID\n        inputParameters:\n  \
  \      - name: parcelId\n          in: path\n          type: string\n          required: true\n          description: LightBox parcel identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: zoning-us-address\n      path: /zoning/us/address\n      operations:\n      - name: getzoningbyaddress\n        method: GET\n        description: Get zoning by address\n        inputParameters:\n        - name: address\n          in: query\n          type: string\n          required: true\n          description: Full street address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: zoning-us-geometry\n      path: /zoning/us/geometry\n      operations:\n      - name: getzoningbygeometry\n        method: POST\n        description: Get zoning by geometry\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lightbox-zoning-api-rest\n    description: REST adapter for LightBox Zoning API.\n    resources:\n    - path: /zoning/us/parcel/{parcelId}\n      name: getzoningbyparcel\n      operations:\n      - method: GET\n        name: getzoningbyparcel\n        description: Get zoning by parcel ID\n        call: lightbox-zoning-api.getzoningbyparcel\n        with:\n          parcelId: rest.parcelId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /zoning/us/address\n      name: getzoningbyaddress\n      operations:\n      - method: GET\n        name: getzoningbyaddress\n        description: Get zoning by address\n        call: lightbox-zoning-api.getzoningbyaddress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /zoning/us/geometry\n      name: getzoningbygeometry\n      operations:\n      - method: POST\n\
  \        name: getzoningbygeometry\n        description: Get zoning by geometry\n        call: lightbox-zoning-api.getzoningbygeometry\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lightbox-zoning-api-mcp\n    transport: http\n    description: MCP adapter for LightBox Zoning API for AI agent use.\n    tools:\n    - name: getzoningbyparcel\n      description: Get zoning by parcel ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lightbox-zoning-api.getzoningbyparcel\n      with:\n        parcelId: tools.parcelId\n      inputParameters:\n      - name: parcelId\n        type: string\n        description: LightBox parcel identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getzoningbyaddress\n      description: Get zoning by address\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: lightbox-zoning-api.getzoningbyaddress\n      with:\n        address: tools.address\n      inputParameters:\n      - name: address\n        type: string\n        description: Full street address\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getzoningbygeometry\n      description: Get zoning by geometry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lightbox-zoning-api.getzoningbygeometry\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LIGHTBOX_ZONING_API_TOKEN: LIGHTBOX_ZONING_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lightbox-zoning-api/refs/heads/main/capabilities/lightbox-zoning-api-capability.yaml
tags:
- Lightbox
- Zoning
- Api
- API
tools:
- description: Get zoning by parcel ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getzoningbyparcel
- description: Get zoning by address
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getzoningbyaddress
- description: Get zoning by geometry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getzoningbygeometry
---
