---
categories: []
consumed_apis: []
description: Open Brewery DB is a free dataset and API with public information on breweries, cideries, brewpubs, and bottleshops.
layout: capability
name: Open Brewery DB
operations:
- description: Open Brewery DB List Breweries
  method: GET
  name: get-breweries
  path: /breweries
- description: Open Brewery DB Single Brewery
  method: GET
  name: get-breweries-obdb-id
  path: /breweries/{obdb-id}
- description: Open Brewery DB Random Brewery
  method: GET
  name: get-breweries-random
  path: /breweries/random
- description: Open Brewery DB Search Breweries
  method: GET
  name: get-breweries-search
  path: /breweries/search
- description: Open Brewery DB Autocomplete
  method: GET
  name: get-breweries-autocomplete
  path: /breweries/autocomplete
- description: Open Brewery DB Metadata
  method: GET
  name: get-breweries-meta
  path: /breweries/meta
personas: []
provider_name: Open Brewery DB
provider_slug: open-brewery-db
search_terms:
- open brewery db single brewery
- cider
- brewery
- open brewery db list breweries
- breweries
- api
- db
- beer
- open brewery db random brewery
- get breweries autocomplete
- get breweries obdb id
- open
- get breweries
- get breweries meta
- bottle shops
- get breweries random
- open brewery db search breweries
- brew pubs
- open brewery db metadata
- get breweries search
- open brewery db autocomplete
slug: open-brewery-db-capability
source_filename: open-brewery-db-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Open Brewery DB\n  description: Open Brewery DB is a free dataset and API with public information on breweries, cideries, brewpubs, and bottleshops.\n  tags:\n  - Open\n  - Brewery\n  - Db\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: open-brewery-db\n    baseUri: https://api.openbrewerydb.org/v1\n    description: Open Brewery DB HTTP API.\n    resources:\n    - name: breweries\n      path: /breweries\n      operations:\n      - name: get-breweries\n        method: GET\n        description: Open Brewery DB List Breweries\n        inputParameters:\n        - name: by_city\n          in: query\n          type: string\n          description: Filter by city name.\n        - name: by_state\n          in: query\n          type: string\n          description: Filter by state name (no abbreviations).\n        - name: by_country\n          in: query\n          type: string\n\
  \          description: Filter by country name.\n        - name: by_type\n          in: query\n          type: string\n          description: Filter by brewery type.\n        - name: by_postal\n          in: query\n          type: string\n          description: Filter by postal code.\n        - name: per_page\n          in: query\n          type: integer\n          description: Number of breweries per page (default 50, max 200).\n        - name: page\n          in: query\n          type: integer\n          description: Page number for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: breweries-obdb-id\n      path: /breweries/{obdb-id}\n      operations:\n      - name: get-breweries-obdb-id\n        method: GET\n        description: Open Brewery DB Single Brewery\n        inputParameters:\n        - name: obdb-id\n          in: path\n          type: string\n          required: true\n  \
  \        description: The ID of the brewery.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: breweries-random\n      path: /breweries/random\n      operations:\n      - name: get-breweries-random\n        method: GET\n        description: Open Brewery DB Random Brewery\n        inputParameters:\n        - name: size\n          in: query\n          type: integer\n          description: Number of breweries to return (default 1, max 50).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: breweries-search\n      path: /breweries/search\n      operations:\n      - name: get-breweries-search\n        method: GET\n        description: Open Brewery DB Search Breweries\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          description: Search term.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: breweries-autocomplete\n      path: /breweries/autocomplete\n      operations:\n      - name: get-breweries-autocomplete\n        method: GET\n        description: Open Brewery DB Autocomplete\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          description: Search term.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: breweries-meta\n      path: /breweries/meta\n      operations:\n      - name: get-breweries-meta\n        method: GET\n        description: Open Brewery DB Metadata\n        inputParameters:\n        - name: by_city\n          in: query\n          type: string\n        - name: by_state\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: open-brewery-db-rest\n    description: REST adapter for Open Brewery DB.\n    resources:\n    - path: /breweries\n      name: get-breweries\n      operations:\n      - method: GET\n        name: get-breweries\n        description: Open Brewery DB List Breweries\n        call: open-brewery-db.get-breweries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /breweries/{obdb-id}\n      name: get-breweries-obdb-id\n      operations:\n      - method: GET\n        name: get-breweries-obdb-id\n        description: Open Brewery DB Single Brewery\n        call: open-brewery-db.get-breweries-obdb-id\n        with:\n          obdb-id: rest.obdb-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /breweries/random\n      name: get-breweries-random\n      operations:\n      - method: GET\n        name: get-breweries-random\n \
  \       description: Open Brewery DB Random Brewery\n        call: open-brewery-db.get-breweries-random\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /breweries/search\n      name: get-breweries-search\n      operations:\n      - method: GET\n        name: get-breweries-search\n        description: Open Brewery DB Search Breweries\n        call: open-brewery-db.get-breweries-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /breweries/autocomplete\n      name: get-breweries-autocomplete\n      operations:\n      - method: GET\n        name: get-breweries-autocomplete\n        description: Open Brewery DB Autocomplete\n        call: open-brewery-db.get-breweries-autocomplete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /breweries/meta\n      name: get-breweries-meta\n      operations:\n      - method: GET\n        name: get-breweries-meta\n        description: Open\
  \ Brewery DB Metadata\n        call: open-brewery-db.get-breweries-meta\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: open-brewery-db-mcp\n    transport: http\n    description: MCP adapter for Open Brewery DB for AI agent use.\n    tools:\n    - name: get-breweries\n      description: Open Brewery DB List Breweries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-brewery-db.get-breweries\n      with:\n        by_city: tools.by_city\n        by_state: tools.by_state\n        by_country: tools.by_country\n        by_type: tools.by_type\n        by_postal: tools.by_postal\n        per_page: tools.per_page\n        page: tools.page\n      inputParameters:\n      - name: by_city\n        type: string\n        description: Filter by city name.\n      - name: by_state\n        type: string\n        description: Filter by state name (no abbreviations).\n     \
  \ - name: by_country\n        type: string\n        description: Filter by country name.\n      - name: by_type\n        type: string\n        description: Filter by brewery type.\n      - name: by_postal\n        type: string\n        description: Filter by postal code.\n      - name: per_page\n        type: integer\n        description: Number of breweries per page (default 50, max 200).\n      - name: page\n        type: integer\n        description: Page number for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-breweries-obdb-id\n      description: Open Brewery DB Single Brewery\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-brewery-db.get-breweries-obdb-id\n      with:\n        obdb-id: tools.obdb-id\n      inputParameters:\n      - name: obdb-id\n        type: string\n        description: The ID of the brewery.\n        required: true\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: get-breweries-random\n      description: Open Brewery DB Random Brewery\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-brewery-db.get-breweries-random\n      with:\n        size: tools.size\n      inputParameters:\n      - name: size\n        type: integer\n        description: Number of breweries to return (default 1, max 50).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-breweries-search\n      description: Open Brewery DB Search Breweries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-brewery-db.get-breweries-search\n      with:\n        query: tools.query\n      inputParameters:\n      - name: query\n        type: string\n        description: Search term.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-breweries-autocomplete\n      description:\
  \ Open Brewery DB Autocomplete\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-brewery-db.get-breweries-autocomplete\n      with:\n        query: tools.query\n      inputParameters:\n      - name: query\n        type: string\n        description: Search term.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-breweries-meta\n      description: Open Brewery DB Metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-brewery-db.get-breweries-meta\n      with:\n        by_city: tools.by_city\n        by_state: tools.by_state\n      inputParameters:\n      - name: by_city\n        type: string\n        description: by_city\n      - name: by_state\n        type: string\n        description: by_state\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/open-brewery-db/refs/heads/main/capabilities/open-brewery-db-capability.yaml
tags:
- Open
- Brewery
- Db
- API
tools:
- description: Open Brewery DB List Breweries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-breweries
- description: Open Brewery DB Single Brewery
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-breweries-obdb-id
- description: Open Brewery DB Random Brewery
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-breweries-random
- description: Open Brewery DB Search Breweries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-breweries-search
- description: Open Brewery DB Autocomplete
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-breweries-autocomplete
- description: Open Brewery DB Metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-breweries-meta
---
