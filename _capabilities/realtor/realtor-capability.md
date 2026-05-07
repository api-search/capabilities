---
categories: []
consumed_apis: []
description: The Realtor.com Property Data API provides programmatic access to real estate listing data from Realtor.com, one of the largest property listing platforms in the United States. It offers endpoints for searching properties by location, price range, bedrooms, bathrooms, and other criteria, as well as retrieving detailed property information including listing status, photos, and neighborhood data. The API supports both for-sale and for-rent property searches and provides access to school ratings, market trends, and comparable property data that developers can use to build real estate applications
layout: capability
name: Realtor.com Property Data API
operations:
- description: Auto-complete locations
  method: GET
  name: autocompletelocations
  path: /locations/v2/auto-complete
- description: List properties
  method: POST
  name: listproperties
  path: /properties/v3/list
- description: Get property detail
  method: GET
  name: getpropertydetail
  path: /properties/v2/detail
- description: List properties by MLS
  method: GET
  name: listpropertiesbymls
  path: /properties/v2/list-by-mls
- description: List similar homes for sale
  method: GET
  name: listsimilarhomes
  path: /properties/v2/list-similar-homes
- description: List similar rental homes
  method: GET
  name: listsimilarrentalhomes
  path: /properties/v2/list-similar-rental-homes
- description: List agents
  method: GET
  name: listagents
  path: /agents/list
- description: Get mortgage rates
  method: GET
  name: getmortgagerates
  path: /finance/rates
personas: []
provider_name: realtor
provider_slug: realtor
search_terms:
- list similar rental homes
- getpropertydetail
- get property detail
- realtor
- list properties by mls
- listsimilarrentalhomes
- list similar homes for sale
- listproperties
- listagents
- auto-complete locations
- list agents
- autocompletelocations
- getmortgagerates
- api
- get mortgage rates
- list properties
- listsimilarhomes
- listpropertiesbymls
slug: realtor-capability
source_filename: realtor-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Realtor.com Property Data API\n  description: The Realtor.com Property Data API provides programmatic access to real estate listing data from Realtor.com,\n    one of the largest property listing platforms in the United States. It offers endpoints for searching properties by location,\n    price range, bedrooms, bathrooms, and other criteria, as well as retrieving detailed property information including listing\n    status, photos, and neighborhood data. The API supports both for-sale and for-rent property searches and provides access\n    to school ratings, market trends, and comparable property data that developers can use to build real estate applications\n  tags:\n  - Realtor\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: realtor\n    baseUri: https://realtor.p.rapidapi.com\n    description: Realtor.com Property Data API HTTP API.\n    authentication:\n      type:\
  \ apikey\n      in: header\n      name: X-RapidAPI-Key\n      value: '{{REALTOR_TOKEN}}'\n    resources:\n    - name: locations-v2-auto-complete\n      path: /locations/v2/auto-complete\n      operations:\n      - name: autocompletelocations\n        method: GET\n        description: Auto-complete locations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: properties-v3-list\n      path: /properties/v3/list\n      operations:\n      - name: listproperties\n        method: POST\n        description: List properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: properties-v2-detail\n      path: /properties/v2/detail\n      operations:\n      - name: getpropertydetail\n        method: GET\n        description: Get property detail\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: properties-v2-list-by-mls\n      path: /properties/v2/list-by-mls\n      operations:\n      - name: listpropertiesbymls\n        method: GET\n        description: List properties by MLS\n        inputParameters:\n        - name: mls_id\n          in: query\n          type: string\n          required: true\n          description: The MLS identifier to search for. Can be a single MLS ID or a comma-separated list of MLS IDs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: properties-v2-list-similar-homes\n      path: /properties/v2/list-similar-homes\n      operations:\n      - name: listsimilarhomes\n        method: GET\n        description: List similar homes for sale\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: properties-v2-list-similar-rental-homes\n\
  \      path: /properties/v2/list-similar-rental-homes\n      operations:\n      - name: listsimilarrentalhomes\n        method: GET\n        description: List similar rental homes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents-list\n      path: /agents/list\n      operations:\n      - name: listagents\n        method: GET\n        description: List agents\n        inputParameters:\n        - name: postal_code\n          in: query\n          type: string\n          description: Postal code to search for agents in a specific area.\n        - name: name\n          in: query\n          type: string\n          description: Agent name to search for.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of results to skip for pagination.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results\
  \ to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: finance-rates\n      path: /finance/rates\n      operations:\n      - name: getmortgagerates\n        method: GET\n        description: Get mortgage rates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: realtor-rest\n    description: REST adapter for Realtor.com Property Data API.\n    resources:\n    - path: /locations/v2/auto-complete\n      name: autocompletelocations\n      operations:\n      - method: GET\n        name: autocompletelocations\n        description: Auto-complete locations\n        call: realtor.autocompletelocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /properties/v3/list\n      name: listproperties\n      operations:\n      - method:\
  \ POST\n        name: listproperties\n        description: List properties\n        call: realtor.listproperties\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /properties/v2/detail\n      name: getpropertydetail\n      operations:\n      - method: GET\n        name: getpropertydetail\n        description: Get property detail\n        call: realtor.getpropertydetail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /properties/v2/list-by-mls\n      name: listpropertiesbymls\n      operations:\n      - method: GET\n        name: listpropertiesbymls\n        description: List properties by MLS\n        call: realtor.listpropertiesbymls\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /properties/v2/list-similar-homes\n      name: listsimilarhomes\n      operations:\n      - method: GET\n        name: listsimilarhomes\n        description: List similar homes for sale\n      \
  \  call: realtor.listsimilarhomes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /properties/v2/list-similar-rental-homes\n      name: listsimilarrentalhomes\n      operations:\n      - method: GET\n        name: listsimilarrentalhomes\n        description: List similar rental homes\n        call: realtor.listsimilarrentalhomes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /agents/list\n      name: listagents\n      operations:\n      - method: GET\n        name: listagents\n        description: List agents\n        call: realtor.listagents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /finance/rates\n      name: getmortgagerates\n      operations:\n      - method: GET\n        name: getmortgagerates\n        description: Get mortgage rates\n        call: realtor.getmortgagerates\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9090\n    namespace: realtor-mcp\n    transport: http\n    description: MCP adapter for Realtor.com Property Data API for AI agent use.\n    tools:\n    - name: autocompletelocations\n      description: Auto-complete locations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: realtor.autocompletelocations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproperties\n      description: List properties\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: realtor.listproperties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpropertydetail\n      description: Get property detail\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: realtor.getpropertydetail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpropertiesbymls\n\
  \      description: List properties by MLS\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: realtor.listpropertiesbymls\n      with:\n        mls_id: tools.mls_id\n      inputParameters:\n      - name: mls_id\n        type: string\n        description: The MLS identifier to search for. Can be a single MLS ID or a comma-separated list of MLS IDs.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsimilarhomes\n      description: List similar homes for sale\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: realtor.listsimilarhomes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsimilarrentalhomes\n      description: List similar rental homes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: realtor.listsimilarrentalhomes\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listagents\n      description: List agents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: realtor.listagents\n      with:\n        postal_code: tools.postal_code\n        name: tools.name\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: postal_code\n        type: string\n        description: Postal code to search for agents in a specific area.\n      - name: name\n        type: string\n        description: Agent name to search for.\n      - name: offset\n        type: integer\n        description: Number of results to skip for pagination.\n      - name: limit\n        type: integer\n        description: Maximum number of results to return.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmortgagerates\n      description: Get mortgage rates\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: realtor.getmortgagerates\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    REALTOR_TOKEN: REALTOR_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/realtor/refs/heads/main/capabilities/realtor-capability.yaml
tags:
- Realtor
- API
tools:
- description: Auto-complete locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: autocompletelocations
- description: List properties
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listproperties
- description: Get property detail
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpropertydetail
- description: List properties by MLS
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpropertiesbymls
- description: List similar homes for sale
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsimilarhomes
- description: List similar rental homes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsimilarrentalhomes
- description: List agents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listagents
- description: Get mortgage rates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmortgagerates
---
