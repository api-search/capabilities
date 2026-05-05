---
api_specs:
- filename: sam-gov-location-services-openapi.yml
  format: yaml
  label: sam-location
  slug: sam-location
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sam.gov/refs/heads/main/openapi/sam-gov-location-services-openapi.yml
categories: []
consumed_apis:
- sam-location
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
- validated state and province data from sam.gov
- federal government
- validate a zip code against sam.gov location data for vendor registration accuracy
- government
- get cities
- gsa
- vendor registration
- look up and validate city names against sam.gov for vendor address submission
- look up and validate us states and international provinces against sam.gov
- zip code validation against sam.gov data
- validate a zip code for sam.gov submission
- procurement
- location services
- get list of cities for vendor address validation
- validated city data from sam.gov
- validate zip code
- entity management
- federal procurement
- lookup states
- contracts
- location validation
- get states
- get list of states for vendor address validation
- lookup cities
- sam.gov
slug: federal-procurement
source_filename: federal-procurement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAM.gov Federal Procurement\"\n  description: >-\n    Federal procurement workflow for validating vendor registration data against\n    SAM.gov location services. Used by government contractors, procurement officers,\n    and vendor registration systems to validate address data before submission to SAM.gov.\n  tags:\n    - Government\n    - Federal Procurement\n    - Location Validation\n    - Vendor Registration\n    - GSA\n    - SAM.gov\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAM_GOV_API_KEY: SAM_GOV_API_KEY\n\ncapability:\n  consumes:\n    - import: sam-location\n      location: ./shared/sam-gov-location-services.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: federal-procurement-api\n      description: \"Unified REST API for SAM.gov federal procurement location validation.\"\n      resources:\n        - path: /v1/cities\n          name:\
  \ cities\n          description: \"Validated city data from SAM.gov\"\n          operations:\n            - method: GET\n              name: get-cities\n              description: \"Get list of cities for vendor address validation\"\n              call: \"sam-location.get-cities\"\n              with:\n                cc: \"rest.cc\"\n                q: \"rest.q\"\n                active: \"rest.active\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/states\n          name: states\n          description: \"Validated state and province data from SAM.gov\"\n          operations:\n            - method: GET\n              name: get-states\n              description: \"Get list of states for vendor address validation\"\n              call: \"sam-location.get-states\"\n              with:\n                cc: \"rest.cc\"\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/zip-codes\n          name: zip-codes\n          description: \"ZIP code validation against SAM.gov data\"\n          operations:\n            - method: GET\n              name: validate-zip-code\n              description: \"Validate a ZIP code for SAM.gov submission\"\n              call: \"sam-location.validate-zip-code\"\n              with:\n                zip: \"rest.zip\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: federal-procurement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted federal procurement and SAM.gov location validation.\"\n      tools:\n        - name: lookup-cities\n          description: \"Look up and validate city names against SAM.gov for vendor address submission\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n\
  \          call: \"sam-location.get-cities\"\n          with:\n            cc: \"tools.country_code\"\n            q: \"tools.city_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: lookup-states\n          description: \"Look up and validate US states and international provinces against SAM.gov\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"sam-location.get-states\"\n          with:\n            cc: \"tools.country_code\"\n            q: \"tools.state_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: validate-zip-code\n          description: \"Validate a ZIP code against SAM.gov location data for vendor registration accuracy\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"sam-location.validate-zip-code\"\n\
  \          with:\n            zip: \"tools.zip_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
