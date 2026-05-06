---
categories: []
consumed_apis: []
description: RealEstateAPI.com provides expressive property data APIs for prop-tech applications. Endpoints include property search, property detail, comparables, AVM (automated valuation), parcel boundary lookups, MLS data, skip tracing, and involuntary lien data. All endpoints accept JSON and require an x-api-key header.
layout: capability
name: RealEstateAPI
operations:
- description: Search properties
  method: POST
  name: post-v2-propertysearch
  path: /v2/PropertySearch
- description: Get a detailed property record
  method: POST
  name: post-v2-propertydetail
  path: /v2/PropertyDetail
- description: Retrieve comparable properties
  method: POST
  name: post-v2-propertycomps
  path: /v2/PropertyComps
- description: Automated valuation
  method: POST
  name: post-v2-avm
  path: /v2/AVM
- description: Retrieve a property's parcel boundary (GeoJSON)
  method: POST
  name: post-v2-propertyboundary
  path: /v2/PropertyBoundary
- description: Search MLS active and historical listings
  method: POST
  name: post-v2-mlssearch
  path: /v2/MLSSearch
- description: Retrieve MLS listing detail
  method: POST
  name: post-v2-mlsdetail
  path: /v2/MLSDetail
- description: Skip trace an owner
  method: POST
  name: post-v2-skiptrace
  path: /v2/SkipTrace
- description: Search involuntary liens
  method: POST
  name: post-v2-involuntaryliens
  path: /v2/InvoluntaryLiens
personas: []
provider_name: RealEstateAPI
provider_slug: realestateapi
search_terms:
- valuation
- prop-tech
- geospatial
- post v2 propertydetail
- search properties
- post v2 propertycomps
- real estate
- search involuntary liens
- search mls active and historical listings
- retrieve mls listing detail
- post v2 propertysearch
- post v2 mlssearch
- realestateapi
- property data
- post v2 skiptrace
- api
- mls
- skip trace an owner
- retrieve comparable properties
- post v2 propertyboundary
- automated valuation
- post v2 involuntaryliens
- skip tracing
- post v2 mlsdetail
- get a detailed property record
- retrieve a property's parcel boundary (geojson)
- post v2 avm
slug: realestateapi-capability
source_filename: realestateapi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RealEstateAPI\n  description: RealEstateAPI.com provides expressive property data APIs for prop-tech applications. Endpoints include property\n    search, property detail, comparables, AVM (automated valuation), parcel boundary lookups, MLS data, skip tracing, and\n    involuntary lien data. All endpoints accept JSON and require an x-api-key header.\n  tags:\n  - Realestateapi\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: realestateapi\n    baseUri: https://api.realestateapi.com\n    description: RealEstateAPI HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{REALESTATEAPI_TOKEN}}'\n    resources:\n    - name: v2-propertysearch\n      path: /v2/PropertySearch\n      operations:\n      - name: post-v2-propertysearch\n        method: POST\n        description: Search properties\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-propertydetail\n      path: /v2/PropertyDetail\n      operations:\n      - name: post-v2-propertydetail\n        method: POST\n        description: Get a detailed property record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-propertycomps\n      path: /v2/PropertyComps\n      operations:\n      - name: post-v2-propertycomps\n        method: POST\n        description: Retrieve comparable properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-avm\n      path: /v2/AVM\n      operations:\n      - name: post-v2-avm\n        method: POST\n        description: Automated valuation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: v2-propertyboundary\n      path: /v2/PropertyBoundary\n      operations:\n      - name: post-v2-propertyboundary\n        method: POST\n        description: Retrieve a property's parcel boundary (GeoJSON)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-mlssearch\n      path: /v2/MLSSearch\n      operations:\n      - name: post-v2-mlssearch\n        method: POST\n        description: Search MLS active and historical listings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-mlsdetail\n      path: /v2/MLSDetail\n      operations:\n      - name: post-v2-mlsdetail\n        method: POST\n        description: Retrieve MLS listing detail\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-skiptrace\n\
  \      path: /v2/SkipTrace\n      operations:\n      - name: post-v2-skiptrace\n        method: POST\n        description: Skip trace an owner\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-involuntaryliens\n      path: /v2/InvoluntaryLiens\n      operations:\n      - name: post-v2-involuntaryliens\n        method: POST\n        description: Search involuntary liens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: realestateapi-rest\n    description: REST adapter for RealEstateAPI.\n    resources:\n    - path: /v2/PropertySearch\n      name: post-v2-propertysearch\n      operations:\n      - method: POST\n        name: post-v2-propertysearch\n        description: Search properties\n        call: realestateapi.post-v2-propertysearch\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v2/PropertyDetail\n      name: post-v2-propertydetail\n      operations:\n      - method: POST\n        name: post-v2-propertydetail\n        description: Get a detailed property record\n        call: realestateapi.post-v2-propertydetail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/PropertyComps\n      name: post-v2-propertycomps\n      operations:\n      - method: POST\n        name: post-v2-propertycomps\n        description: Retrieve comparable properties\n        call: realestateapi.post-v2-propertycomps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/AVM\n      name: post-v2-avm\n      operations:\n      - method: POST\n        name: post-v2-avm\n        description: Automated valuation\n        call: realestateapi.post-v2-avm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/PropertyBoundary\n\
  \      name: post-v2-propertyboundary\n      operations:\n      - method: POST\n        name: post-v2-propertyboundary\n        description: Retrieve a property's parcel boundary (GeoJSON)\n        call: realestateapi.post-v2-propertyboundary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/MLSSearch\n      name: post-v2-mlssearch\n      operations:\n      - method: POST\n        name: post-v2-mlssearch\n        description: Search MLS active and historical listings\n        call: realestateapi.post-v2-mlssearch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/MLSDetail\n      name: post-v2-mlsdetail\n      operations:\n      - method: POST\n        name: post-v2-mlsdetail\n        description: Retrieve MLS listing detail\n        call: realestateapi.post-v2-mlsdetail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/SkipTrace\n      name: post-v2-skiptrace\n   \
  \   operations:\n      - method: POST\n        name: post-v2-skiptrace\n        description: Skip trace an owner\n        call: realestateapi.post-v2-skiptrace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/InvoluntaryLiens\n      name: post-v2-involuntaryliens\n      operations:\n      - method: POST\n        name: post-v2-involuntaryliens\n        description: Search involuntary liens\n        call: realestateapi.post-v2-involuntaryliens\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: realestateapi-mcp\n    transport: http\n    description: MCP adapter for RealEstateAPI for AI agent use.\n    tools:\n    - name: post-v2-propertysearch\n      description: Search properties\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: realestateapi.post-v2-propertysearch\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: post-v2-propertydetail\n      description: Get a detailed property record\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: realestateapi.post-v2-propertydetail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v2-propertycomps\n      description: Retrieve comparable properties\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: realestateapi.post-v2-propertycomps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v2-avm\n      description: Automated valuation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: realestateapi.post-v2-avm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v2-propertyboundary\n      description: Retrieve a property's parcel boundary (GeoJSON)\n      hints:\n  \
  \      readOnly: false\n        destructive: false\n        idempotent: false\n      call: realestateapi.post-v2-propertyboundary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v2-mlssearch\n      description: Search MLS active and historical listings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: realestateapi.post-v2-mlssearch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v2-mlsdetail\n      description: Retrieve MLS listing detail\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: realestateapi.post-v2-mlsdetail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v2-skiptrace\n      description: Skip trace an owner\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: realestateapi.post-v2-skiptrace\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v2-involuntaryliens\n      description: Search involuntary liens\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: realestateapi.post-v2-involuntaryliens\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    REALESTATEAPI_TOKEN: REALESTATEAPI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/realestateapi/refs/heads/main/capabilities/realestateapi-capability.yaml
tags:
- Realestateapi
- API
tools:
- description: Search properties
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-propertysearch
- description: Get a detailed property record
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-propertydetail
- description: Retrieve comparable properties
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-propertycomps
- description: Automated valuation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-avm
- description: Retrieve a property's parcel boundary (GeoJSON)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-propertyboundary
- description: Search MLS active and historical listings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-mlssearch
- description: Retrieve MLS listing detail
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-mlsdetail
- description: Skip trace an owner
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-skiptrace
- description: Search involuntary liens
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-involuntaryliens
---
