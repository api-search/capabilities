---
categories: []
consumed_apis: []
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
- fraud detection
- submit a transaction as an acquirer
- submit acquirer transaction
- financial services
- track
- search for merchant places
- locations
- search for atm locations
- merchant location search
- search for merchants in the mastercard track network
- search atm locations
- list countries with merchant locations
- credit cards
- search track merchants
- search for mastercard atm locations
- list atm countries
- digital identity
- open banking
- list merchant countries
- search merchant locations
- list countries with mastercard atms
- search for merchant places with location intelligence
- search places
- mastercard
- search for merchants in track
- track merchant data
- acquirer
- atm location search
- payments
- places location intelligence
- search for mastercard merchant locations
- merchant
- search for merchant locations
slug: merchant-services-and-locations
source_filename: merchant-services-and-locations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Merchant Services and Locations\n  description: Unified workflow for merchants and acquirers to manage merchant/ATM locations, Places data, Track merchant\n    search, and acquirer transaction processing.\n  tags:\n  - Mastercard\n  - Merchant\n  - Locations\n  - Acquirer\n  - Track\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: merchant-locations\n    baseUri: https://api.mastercard.com/locations/merchants\n    description: Mastercard Merchant Locations API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: countries\n      path: /countries\n      description: Country data for merchant locations\n      operations:\n\
  \      - name: get-countries\n        method: GET\n        description: Returns a list of countries with merchant locations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: searches\n      path: /searches\n      description: Merchant location search operations\n      operations:\n      - name: search-merchants\n        method: POST\n        description: Search for merchant locations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            location: '{{tools.location}}'\n  - type: http\n    namespace: atm-locations\n    baseUri: https://api.mastercard.com/locations/atms\n    description: Mastercard ATM Locations API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n\
  \    - name: countries\n      path: /countries\n      description: Country and subdivision data for ATM locations\n      operations:\n      - name: get-countries\n        method: GET\n        description: Returns a list of countries containing ATMs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-country-subdivisions\n        method: GET\n        description: Returns a list of country subdivisions for a given country\n        inputParameters:\n        - name: country_code\n          in: query\n          type: string\n          required: true\n          description: Country code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: searches\n      path: /searches\n      description: ATM search operations\n      operations:\n      - name: search-atms\n        method: POST\n        description: Search for ATMs\
  \ by location and features\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            location: '{{tools.location}}'\n  - type: http\n    namespace: places\n    baseUri: https://api.mastercard.com/places\n    description: Mastercard Places API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: places\n      path: /places\n      description: Place search and data\n      operations:\n      - name: search-places\n        method: POST\n        description: Search for merchant places\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            search: '{{tools.search}}'\n  - type: http\n    namespace: track-search\n\
  \    baseUri: https://api.mastercard.com/track/search\n    description: Mastercard Track Search API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: searches\n      path: /searches\n      description: Track search operations\n      operations:\n      - name: search-merchants\n        method: POST\n        description: Search for merchants in Track\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            search: '{{tools.search}}'\n  - type: http\n    namespace: transaction-api-acquirers\n    baseUri: https://api.mastercard.com/transactions/acquirers\n    description: Mastercard Transaction API for Acquirers\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n\
  \    resources:\n    - name: transactions\n      path: /transactions\n      description: Acquirer transaction operations\n      operations:\n      - name: submit-transaction\n        method: POST\n        description: Submit a transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transaction: '{{tools.transaction}}'\n  exposes:\n  - type: rest\n    port: 8091\n    namespace: merchant-services-api\n    description: Unified REST API for merchant services and location data.\n    resources:\n    - path: /v1/merchant-locations\n      name: merchant-locations\n      description: Merchant location search\n      operations:\n      - method: POST\n        name: search-merchant-locations\n        description: Search for merchant locations\n        call: merchant-locations.search-merchants\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /v1/atm-locations\n      name: atm-locations\n      description: ATM location search\n      operations:\n      - method: POST\n        name: search-atm-locations\n        description: Search for ATM locations\n        call: atm-locations.search-atms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/places\n      name: places\n      description: Places location intelligence\n      operations:\n      - method: POST\n        name: search-places\n        description: Search for merchant places\n        call: places.search-places\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/track-merchants\n      name: track-merchants\n      description: Track merchant data\n      operations:\n      - method: POST\n        name: search-track-merchants\n        description: Search for merchants in Track\n        call: track-search.search-merchants\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9101\n    namespace: merchant-services-mcp\n    transport: http\n    description: MCP server for AI-assisted merchant services and location queries.\n    tools:\n    - name: search-merchant-locations\n      description: Search for Mastercard merchant locations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: merchant-locations.search-merchants\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-merchant-countries\n      description: List countries with merchant locations\n      hints:\n        readOnly: true\n        idempotent: true\n      call: merchant-locations.get-countries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-atm-locations\n      description: Search for Mastercard ATM locations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: atm-locations.search-atms\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-atm-countries\n      description: List countries with Mastercard ATMs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: atm-locations.get-countries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-places\n      description: Search for merchant places with location intelligence\n      hints:\n        readOnly: true\n        openWorld: true\n      call: places.search-places\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-track-merchants\n      description: Search for merchants in the Mastercard Track network\n      hints:\n        readOnly: true\n      call: track-search.search-merchants\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-acquirer-transaction\n      description: Submit a transaction as an acquirer\n      hints:\n        readOnly: false\n      call: transaction-api-acquirers.submit-transaction\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
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
