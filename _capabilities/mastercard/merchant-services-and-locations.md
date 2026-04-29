---
categories: []
consumed_apis:
- merchant-locations
- atm-locations
- places
- track-search
- transaction-api-acquirers
description: Unified workflow for merchants and acquirers to manage merchant/ATM locations, Places data, Track merchant search, and acquirer transaction processing.
layout: capability
name: Mastercard Merchant Services and Locations
operations:
- description: Search for merchant locations
  method: POST
  name: search-merchant-locations
  path: /v1/merchant-locations
- description: Search for ATM locations
  method: POST
  name: search-atm-locations
  path: /v1/atm-locations
- description: Search for merchant places
  method: POST
  name: search-places
  path: /v1/places
- description: Search for merchants in Track
  method: POST
  name: search-track-merchants
  path: /v1/track-merchants
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- payments
- search for merchant places
- open banking
- list countries with merchant locations
- locations
- search for atm locations
- search for merchants in the mastercard track network
- list atm countries
- search atm locations
- track merchant data
- list countries with mastercard atms
- submit a transaction as an acquirer
- list merchant countries
- search track merchants
- search for mastercard merchant locations
- digital identity
- search for merchants in track
- acquirer
- mastercard
- credit cards
- search places
- submit acquirer transaction
- places location intelligence
- search for merchant locations
- financial services
- track
- search for merchant places with location intelligence
- fraud detection
- search merchant locations
- merchant
- merchant location search
- atm location search
- search for mastercard atm locations
slug: merchant-services-and-locations
source_filename: merchant-services-and-locations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Mastercard Merchant Services and Locations\"\n  description: \"Unified workflow for merchants and acquirers to manage merchant/ATM locations, Places data, Track merchant search, and acquirer transaction processing.\"\n  tags:\n    - Mastercard\n    - Merchant\n    - Locations\n    - Acquirer\n    - Track\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n      MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\n\ncapability:\n  consumes:\n    - import: merchant-locations\n      location: ./shared/merchant-locations.yaml\n    - import: atm-locations\n      location: ./shared/atm-locations.yaml\n    - import: places\n      location: ./shared/places.yaml\n    - import: track-search\n      location: ./shared/track-search.yaml\n    - import: transaction-api-acquirers\n      location: ./shared/transaction-api-acquirers.yaml\n\n  exposes:\n\
  \    - type: rest\n      port: 8091\n      namespace: merchant-services-api\n      description: \"Unified REST API for merchant services and location data.\"\n      resources:\n        - path: /v1/merchant-locations\n          name: merchant-locations\n          description: \"Merchant location search\"\n          operations:\n            - method: POST\n              name: search-merchant-locations\n              description: \"Search for merchant locations\"\n              call: \"merchant-locations.search-merchants\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/atm-locations\n          name: atm-locations\n          description: \"ATM location search\"\n          operations:\n            - method: POST\n              name: search-atm-locations\n              description: \"Search for ATM locations\"\n              call: \"atm-locations.search-atms\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/places\n          name: places\n          description: \"Places location intelligence\"\n          operations:\n            - method: POST\n              name: search-places\n              description: \"Search for merchant places\"\n              call: \"places.search-places\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/track-merchants\n          name: track-merchants\n          description: \"Track merchant data\"\n          operations:\n            - method: POST\n              name: search-track-merchants\n              description: \"Search for merchants in Track\"\n              call: \"track-search.search-merchants\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9101\n      namespace: merchant-services-mcp\n      transport: http\n      description: \"MCP server for\
  \ AI-assisted merchant services and location queries.\"\n      tools:\n        - name: search-merchant-locations\n          description: \"Search for Mastercard merchant locations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"merchant-locations.search-merchants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-merchant-countries\n          description: \"List countries with merchant locations\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"merchant-locations.get-countries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-atm-locations\n          description: \"Search for Mastercard ATM locations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"atm-locations.search-atms\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: list-atm-countries\n          description: \"List countries with Mastercard ATMs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"atm-locations.get-countries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-places\n          description: \"Search for merchant places with location intelligence\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"places.search-places\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-track-merchants\n          description: \"Search for merchants in the Mastercard Track network\"\n          hints:\n            readOnly: true\n          call: \"track-search.search-merchants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-acquirer-transaction\n\
  \          description: \"Submit a transaction as an acquirer\"\n          hints:\n            readOnly: false\n          call: \"transaction-api-acquirers.submit-transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/merchant-services-and-locations.yaml
tags:
- Mastercard
- Merchant
- Locations
- Acquirer
- Track
tools:
- description: Search for Mastercard merchant locations
  hints:
    openWorld: true
    readOnly: true
  name: search-merchant-locations
- description: List countries with merchant locations
  hints:
    idempotent: true
    readOnly: true
  name: list-merchant-countries
- description: Search for Mastercard ATM locations
  hints:
    openWorld: true
    readOnly: true
  name: search-atm-locations
- description: List countries with Mastercard ATMs
  hints:
    idempotent: true
    readOnly: true
  name: list-atm-countries
- description: Search for merchant places with location intelligence
  hints:
    openWorld: true
    readOnly: true
  name: search-places
- description: Search for merchants in the Mastercard Track network
  hints:
    readOnly: true
  name: search-track-merchants
- description: Submit a transaction as an acquirer
  hints:
    readOnly: false
  name: submit-acquirer-transaction
---
