---
categories: []
consumed_apis: []
description: Federal procurement workflow for validating vendor registration data against SAM.gov location services. Used by government contractors, procurement officers, and vendor registration systems to validate address data before submission to SAM.gov.
layout: capability
name: SAM.gov Federal Procurement
operations:
- description: Get list of cities for vendor address validation
  method: GET
  name: get-cities
  path: /v1/cities
- description: Get list of states for vendor address validation
  method: GET
  name: get-states
  path: /v1/states
- description: Validate a ZIP code for SAM.gov submission
  method: GET
  name: validate-zip-code
  path: /v1/zip-codes
personas: []
provider_name: SAM.gov
provider_slug: sam.gov
search_terms:
- procurement
- validated state and province data from sam.gov
- vendor registration
- contracts
- lookup cities
- gsa
- location services
- validate a zip code against sam.gov location data for vendor registration accuracy
- location validation
- validate zip code
- federal procurement
- validated city data from sam.gov
- get cities
- look up and validate us states and international provinces against sam.gov
- entity management
- get list of states for vendor address validation
- validate a zip code for sam.gov submission
- government
- zip code validation against sam.gov data
- sam.gov
- get states
- get list of cities for vendor address validation
- lookup states
- look up and validate city names against sam.gov for vendor address submission
- federal government
slug: federal-procurement
source_filename: federal-procurement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAM.gov Federal Procurement\n  description: Federal procurement workflow for validating vendor registration data against SAM.gov location services. Used\n    by government contractors, procurement officers, and vendor registration systems to validate address data before submission\n    to SAM.gov.\n  tags:\n  - Government\n  - Federal Procurement\n  - Location Validation\n  - Vendor Registration\n  - GSA\n  - SAM.gov\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAM_GOV_API_KEY: SAM_GOV_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sam-location\n    baseUri: https://api.sam.gov\n    description: SAM.gov Public Location Services API\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{SAM_GOV_API_KEY}}'\n      placement: query\n    resources:\n    - name: cities\n      path: /locationservices/v1/cities\n      description: City lookup and validation\n\
  \      operations:\n      - name: get-cities\n        method: GET\n        description: Get a list of cities for a given country code\n        inputParameters:\n        - name: cc\n          in: query\n          type: string\n          required: false\n          description: Country code (ISO 3166-1 alpha-2)\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query for city name\n        - name: active\n          in: query\n          type: string\n          required: false\n          description: Filter active cities (Y/N)\n        - name: citycode\n          in: query\n          type: string\n          required: false\n          description: Filter by city code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: states\n      path: /locationservices/v1/states\n      description: State and province lookup\n      operations:\n    \
  \  - name: get-states\n        method: GET\n        description: Get a list of states and provinces\n        inputParameters:\n        - name: cc\n          in: query\n          type: string\n          required: false\n          description: Country code (ISO 3166-1 alpha-2)\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query for state name\n        - name: active\n          in: query\n          type: string\n          required: false\n          description: Filter active states (Y/N)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: zip\n      path: /locationservices/v1/zip\n      description: ZIP code validation\n      operations:\n      - name: validate-zip-code\n        method: GET\n        description: Validate a ZIP code and get associated city/county data\n        inputParameters:\n        - name: zip\n          in:\
  \ query\n          type: string\n          required: true\n          description: ZIP code to validate\n        - name: statecode\n          in: query\n          type: string\n          required: false\n          description: State code filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: federal-procurement-api\n    description: Unified REST API for SAM.gov federal procurement location validation.\n    resources:\n    - path: /v1/cities\n      name: cities\n      description: Validated city data from SAM.gov\n      operations:\n      - method: GET\n        name: get-cities\n        description: Get list of cities for vendor address validation\n        call: sam-location.get-cities\n        with:\n          cc: rest.cc\n          q: rest.q\n          active: rest.active\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /v1/states\n      name: states\n      description: Validated state and province data from SAM.gov\n      operations:\n      - method: GET\n        name: get-states\n        description: Get list of states for vendor address validation\n        call: sam-location.get-states\n        with:\n          cc: rest.cc\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/zip-codes\n      name: zip-codes\n      description: ZIP code validation against SAM.gov data\n      operations:\n      - method: GET\n        name: validate-zip-code\n        description: Validate a ZIP code for SAM.gov submission\n        call: sam-location.validate-zip-code\n        with:\n          zip: rest.zip\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: federal-procurement-mcp\n    transport: http\n    description: MCP server for AI-assisted federal procurement and SAM.gov location\
  \ validation.\n    tools:\n    - name: lookup-cities\n      description: Look up and validate city names against SAM.gov for vendor address submission\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: sam-location.get-cities\n      with:\n        cc: tools.country_code\n        q: tools.city_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-states\n      description: Look up and validate US states and international provinces against SAM.gov\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: sam-location.get-states\n      with:\n        cc: tools.country_code\n        q: tools.state_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-zip-code\n      description: Validate a ZIP code against SAM.gov location data for vendor registration accuracy\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n        openWorld: true\n      call: sam-location.validate-zip-code\n      with:\n        zip: tools.zip_code\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sam.gov/refs/heads/main/capabilities/federal-procurement.yaml
tags:
- Government
- Federal Procurement
- Location Validation
- Vendor Registration
- GSA
- SAM.gov
tools:
- description: Look up and validate city names against SAM.gov for vendor address submission
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: lookup-cities
- description: Look up and validate US states and international provinces against SAM.gov
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: lookup-states
- description: Validate a ZIP code against SAM.gov location data for vendor registration accuracy
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: validate-zip-code
---
