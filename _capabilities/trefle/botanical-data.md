---
categories: []
consumed_apis: []
description: Workflow capability for Trefle botanical data covering plant search, species detail retrieval, taxonomy navigation, and geographic distribution analysis. Designed for gardening applications, agricultural tools, ecological research platforms, and farming automation systems that need plant species data.
layout: capability
name: Trefle Botanical Data
operations:
- description: List plant species with pagination
  method: GET
  name: list-plants
  path: /v1/plants
- description: Search plants by common or scientific name
  method: GET
  name: search-plants
  path: /v1/plants/search
- description: Get a specific plant by ID or slug
  method: GET
  name: get-plant
  path: /v1/plants/{id}
- description: List species with taxonomy and growth data
  method: GET
  name: list-species
  path: /v1/species
- description: Search species by name
  method: GET
  name: search-species
  path: /v1/species/search
- description: Get full species data including morphology and distribution
  method: GET
  name: get-species
  path: /v1/species/{id}
- description: List all plant families
  method: GET
  name: list-families
  path: /v1/families
- description: List all plant genera
  method: GET
  name: list-genus
  path: /v1/genus
- description: List all distribution zones
  method: GET
  name: list-distributions
  path: /v1/distributions
- description: Get plants native or established in a geographic zone
  method: GET
  name: get-plants-by-distribution
  path: /v1/distributions/{id}/plants
personas: []
provider_name: Trefle
provider_slug: trefle
search_terms:
- list species
- search trefle plant species by name for detailed botanical data
- list geographic distribution zones used in trefle plant range data
- get plants in a specific region
- list families
- list genus
- data api
- get species detail
- search for plants by name
- search species by name
- search plants
- get a specific plant by id or slug
- search the trefle database for plant species by common or scientific name
- plants
- list plants
- get plants native or established in a geographic zone
- list all plant genera in the trefle botanical taxonomy
- list species with taxonomy and growth data
- get comprehensive species data including morphology, growth requirements, and distribution
- browse and discover plant species
- get plant
- search species
- ecology
- browse plant genus taxonomy
- get plants in region
- browse geographic distribution zones
- list plant species from trefle with optional pagination
- science
- list all plant genera
- list distributions
- get plant details
- get full species data including morphology and distribution
- list all distribution zones
- search plants by common or scientific name
- get species
- browse plant family taxonomy
- list plant species with pagination
- browse species with detailed botanical data
- get plants by distribution
- list distribution zones
- botany
- get comprehensive species data
- list all plant families
- get plant species native or established in a specific geographic region
- get basic information about a plant by trefle id or slug
- list plant genera
- list all plant families in the trefle botanical taxonomy
- list plant families
- agriculture
- open data
slug: botanical-data
source_filename: botanical-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trefle Botanical Data\n  description: Workflow capability for Trefle botanical data covering plant search, species detail retrieval, taxonomy navigation,\n    and geographic distribution analysis. Designed for gardening applications, agricultural tools, ecological research platforms,\n    and farming automation systems that need plant species data.\n  tags:\n  - Agriculture\n  - Botany\n  - Data API\n  - Ecology\n  - Open Data\n  - Plants\n  - Science\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TREFLE_TOKEN: TREFLE_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: trefle\n    baseUri: https://trefle.io/api/v1\n    description: Trefle botanical REST API for plant taxonomy, species, and distribution data.\n    authentication:\n      type: apikey\n      key: token\n      value: '{{TREFLE_TOKEN}}'\n      placement: query\n    resources:\n    - name: plants\n      path: /plants\n\
  \      description: Search and browse plant species\n      operations:\n      - name: list-plants\n        method: GET\n        description: Returns a paginated list of plant species\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-plants\n        method: GET\n        description: Search for plants by common or scientific name\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-plant\n        method: GET\n        description: Get detailed\
  \ information about a specific plant\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Plant ID or slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: species\n      path: /species\n      description: Access detailed species data\n      operations:\n      - name: list-species\n        method: GET\n        description: Returns a paginated list of plant species with detailed data\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: filter[common_name]\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-species\n        method: GET\n        description: Search\
  \ species by common or scientific name\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-species\n        method: GET\n        description: Get comprehensive species data including morphology and distributions\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: families\n      path: /families\n      description: Browse plant family taxonomy\n      operations:\n      - name: list-families\n        method: GET\n        description: List all plant families\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: get-family\n        method: GET\n        description: Get a specific plant family\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: genus\n      path: /genus\n      description: Browse plant genus taxonomy\n      operations:\n      - name: list-genus\n        method: GET\n        description: List all plant genera\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-genus\n        method: GET\n        description: Get a specific plant genus\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: distributions\n      path: /distributions\n      description: Access geographic distribution data\n      operations:\n      - name: list-distributions\n        method: GET\n        description: List all geographic distribution zones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-plants-by-distribution\n        method: GET\n        description: Get plants native or established in a specific geographic zone\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Distribution zone slug (e.g., california, france)\n        - name: filter[establishment]\n          in: query\n          type: string\n          required: false\n          description: Filter by establishment type (native, introduced, etc.)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: trefle-botanical-api\n    description: Unified REST API for Trefle botanical data workflows.\n    resources:\n    - path: /v1/plants\n      name: plants\n      description: Browse and discover plant species\n      operations:\n      - method: GET\n        name: list-plants\n        description: List plant species with pagination\n        call: trefle.list-plants\n        with:\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plants/search\n      name: plant-search\n      description: Search for plants by name\n      operations:\n      - method: GET\n        name: search-plants\n        description: Search plants by common or scientific name\n        call: trefle.search-plants\n        with:\n          q: rest.q\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plants/{id}\n\
  \      name: plant-detail\n      description: Get plant details\n      operations:\n      - method: GET\n        name: get-plant\n        description: Get a specific plant by ID or slug\n        call: trefle.get-plant\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/species\n      name: species\n      description: Browse species with detailed botanical data\n      operations:\n      - method: GET\n        name: list-species\n        description: List species with taxonomy and growth data\n        call: trefle.list-species\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/species/search\n      name: species-search\n      description: Search species\n      operations:\n      - method: GET\n        name: search-species\n        description: Search species by name\n        call: trefle.search-species\n        with:\n          q: rest.q\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n    - path: /v1/species/{id}\n      name: species-detail\n      description: Get comprehensive species data\n      operations:\n      - method: GET\n        name: get-species\n        description: Get full species data including morphology and distribution\n        call: trefle.get-species\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/families\n      name: families\n      description: Browse plant family taxonomy\n      operations:\n      - method: GET\n        name: list-families\n        description: List all plant families\n        call: trefle.list-families\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/genus\n      name: genus\n      description: Browse plant genus taxonomy\n      operations:\n      - method: GET\n        name: list-genus\n        description: List all plant genera\n        call: trefle.list-genus\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/distributions\n      name: distributions\n      description: Browse geographic distribution zones\n      operations:\n      - method: GET\n        name: list-distributions\n        description: List all distribution zones\n        call: trefle.list-distributions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/distributions/{id}/plants\n      name: plants-by-distribution\n      description: Get plants in a specific region\n      operations:\n      - method: GET\n        name: get-plants-by-distribution\n        description: Get plants native or established in a geographic zone\n        call: trefle.get-plants-by-distribution\n        with:\n          id: rest.id\n          filter[establishment]: rest.establishment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: trefle-botanical-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted botanical data queries with Trefle.\n    tools:\n    - name: search-plants\n      description: Search the Trefle database for plant species by common or scientific name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trefle.search-plants\n      with:\n        q: tools.q\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-plants\n      description: List plant species from Trefle with optional pagination\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trefle.list-plants\n      with:\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-plant\n      description: Get basic information about a plant by Trefle ID or slug\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trefle.get-plant\n      with:\n        id: tools.id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: search-species\n      description: Search Trefle plant species by name for detailed botanical data\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trefle.search-species\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-species-detail\n      description: Get comprehensive species data including morphology, growth requirements, and distribution\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trefle.get-species\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-plant-families\n      description: List all plant families in the Trefle botanical taxonomy\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trefle.list-families\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-plant-genera\n\
  \      description: List all plant genera in the Trefle botanical taxonomy\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trefle.list-genus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-distribution-zones\n      description: List geographic distribution zones used in Trefle plant range data\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trefle.list-distributions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-plants-in-region\n      description: Get plant species native or established in a specific geographic region\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trefle.get-plants-by-distribution\n      with:\n        id: tools.id\n        filter[establishment]: tools.establishment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trefle/refs/heads/main/capabilities/botanical-data.yaml
tags:
- Agriculture
- Botany
- Data API
- Ecology
- Open Data
- Plants
- Science
tools:
- description: Search the Trefle database for plant species by common or scientific name
  hints:
    openWorld: true
    readOnly: true
  name: search-plants
- description: List plant species from Trefle with optional pagination
  hints:
    openWorld: true
    readOnly: true
  name: list-plants
- description: Get basic information about a plant by Trefle ID or slug
  hints:
    openWorld: false
    readOnly: true
  name: get-plant
- description: Search Trefle plant species by name for detailed botanical data
  hints:
    openWorld: true
    readOnly: true
  name: search-species
- description: Get comprehensive species data including morphology, growth requirements, and distribution
  hints:
    openWorld: false
    readOnly: true
  name: get-species-detail
- description: List all plant families in the Trefle botanical taxonomy
  hints:
    openWorld: true
    readOnly: true
  name: list-plant-families
- description: List all plant genera in the Trefle botanical taxonomy
  hints:
    openWorld: true
    readOnly: true
  name: list-plant-genera
- description: List geographic distribution zones used in Trefle plant range data
  hints:
    openWorld: true
    readOnly: true
  name: list-distribution-zones
- description: Get plant species native or established in a specific geographic region
  hints:
    openWorld: false
    readOnly: true
  name: get-plants-in-region
---
