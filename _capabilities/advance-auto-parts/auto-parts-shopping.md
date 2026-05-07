---
categories: []
consumed_apis: []
description: Unified workflow capability for automotive parts discovery, fitment lookup, inventory checking, ordering, and loyalty management. Designed for automotive technicians, fleet managers, and DIY customers.
layout: capability
name: Advance Auto Parts Shopping
operations:
- description: Search for automotive parts.
  method: GET
  name: search-parts
  path: /v1/parts
- description: Get automotive part details.
  method: GET
  name: get-part
  path: /v1/parts/{productId}
- description: Check part inventory at stores.
  method: GET
  name: check-inventory
  path: /v1/inventory
personas: []
provider_name: Advance Auto Parts
provider_slug: advance-auto-parts
search_terms:
- check inventory
- automotive technician
- search parts
- check part availability
- check if an automotive part is in stock at nearby advance auto parts stores.
- diy customer
- get vehicle years
- do-it-yourself automotive enthusiast sourcing parts for self-repairs
- search for automotive parts.
- loyalty
- retail
- check part inventory at stores.
- store inventory.
- supply chain
- search auto parts
- fleet operations manager ordering parts for vehicle maintenance programs
- get available vehicle makes for a given model year for fitment-based part search.
- find advance auto parts store locations near a zip code or city.
- lookup vehicle models
- search for automotive parts by keyword, part number, or vehicle year/make/model.
- get the range of supported vehicle model years for parts catalog lookups.
- parts catalog search.
- get full specifications, fitment notes, and pricing for a specific automotive part.
- find nearby stores
- professional mechanic using the api to source parts for repair jobs
- get part
- unified workflow for automotive parts discovery, fitment lookup, inventory, and ordering
- e-commerce
- lookup vehicle makes
- advance auto parts
- get part details
- part details.
- parts catalog
- automotive
- get available vehicle models for a year and make for fitment-based part search.
- fleet manager
- get automotive part details.
slug: auto-parts-shopping
source_filename: auto-parts-shopping.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Advance Auto Parts Shopping\n  description: Unified workflow capability for automotive parts discovery, fitment lookup, inventory checking, ordering, and\n    loyalty management. Designed for automotive technicians, fleet managers, and DIY customers.\n  tags:\n  - Advance Auto Parts\n  - Automotive\n  - E-Commerce\n  - Parts Catalog\n  - Loyalty\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AAP_API_KEY: AAP_API_KEY\n    AAP_OAUTH_TOKEN: AAP_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: aap-catalog\n    baseUri: https://api.advanceautoparts.com/v1\n    description: Advance Auto Parts Catalog REST API.\n    authentication:\n      type: apiKey\n      header: X-API-Key\n      token: '{{AAP_API_KEY}}'\n    resources:\n    - name: vehicle-years\n      path: /vehicles/years\n      description: Vehicle year lookup.\n      operations:\n      - name: list-vehicle-years\n      \
  \  method: GET\n        description: List available vehicle model years.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-makes\n      path: /vehicles/makes\n      description: Vehicle make lookup.\n      operations:\n      - name: list-vehicle-makes\n        method: GET\n        description: List vehicle makes for a given year.\n        inputParameters:\n        - name: year\n          in: query\n          type: integer\n          required: true\n          description: Vehicle model year.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-models\n      path: /vehicles/models\n      description: Vehicle model lookup.\n      operations:\n      - name: list-vehicle-models\n        method: GET\n        description: List vehicle models for a given year and make.\n        inputParameters:\n       \
  \ - name: year\n          in: query\n          type: integer\n          required: true\n          description: Vehicle model year.\n        - name: makeId\n          in: query\n          type: string\n          required: true\n          description: Vehicle make identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      description: Parts catalog search.\n      operations:\n      - name: search-products\n        method: GET\n        description: Search for automotive parts by keyword or fitment.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Keyword search query.\n        - name: year\n          in: query\n          type: integer\n          required: false\n          description: Vehicle year for fitment.\n        - name: makeId\n          in: query\n          type:\
  \ string\n          required: false\n          description: Vehicle make ID.\n        - name: modelId\n          in: query\n          type: string\n          required: false\n          description: Vehicle model ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: product\n      path: /products/{productId}\n      description: Product detail lookup.\n      operations:\n      - name: get-product\n        method: GET\n        description: Get full product details.\n        inputParameters:\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product SKU.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory\n      path: /inventory\n      description: Store inventory check.\n      operations:\n      - name: check-inventory\n        method:\
  \ GET\n        description: Check product availability at nearby stores.\n        inputParameters:\n        - name: productId\n          in: query\n          type: string\n          required: true\n          description: Product SKU.\n        - name: zip\n          in: query\n          type: string\n          required: false\n          description: ZIP code for nearby stores.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stores\n      path: /stores\n      description: Store location search.\n      operations:\n      - name: get-stores\n        method: GET\n        description: Find Advance Auto Parts stores near a location.\n        inputParameters:\n        - name: zip\n          in: query\n          type: string\n          required: false\n          description: ZIP code to search near.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8090\n    namespace: aap-shopping-api\n    description: Unified REST API for Advance Auto Parts catalog search, inventory, ordering, and loyalty.\n    resources:\n    - path: /v1/parts\n      name: parts\n      description: Parts catalog search.\n      operations:\n      - method: GET\n        name: search-parts\n        description: Search for automotive parts.\n        call: aap-catalog.search-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parts/{productId}\n      name: part\n      description: Part details.\n      operations:\n      - method: GET\n        name: get-part\n        description: Get automotive part details.\n        call: aap-catalog.get-product\n        with:\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inventory\n      name: inventory\n      description: Store inventory.\n  \
  \    operations:\n      - method: GET\n        name: check-inventory\n        description: Check part inventory at stores.\n        call: aap-catalog.check-inventory\n        with:\n          productId: rest.productId\n          zip: rest.zip\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: aap-shopping-mcp\n    transport: http\n    description: MCP server for AI-assisted automotive parts shopping — find parts, check availability, and manage orders.\n    tools:\n    - name: search-auto-parts\n      description: Search for automotive parts by keyword, part number, or vehicle year/make/model.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aap-catalog.search-products\n      with:\n        q: tools.q\n        year: tools.year\n        makeId: tools.makeId\n        modelId: tools.modelId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-part-details\n     \
  \ description: Get full specifications, fitment notes, and pricing for a specific automotive part.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aap-catalog.get-product\n      with:\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-part-availability\n      description: Check if an automotive part is in stock at nearby Advance Auto Parts stores.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aap-catalog.check-inventory\n      with:\n        productId: tools.productId\n        zip: tools.zip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-nearby-stores\n      description: Find Advance Auto Parts store locations near a ZIP code or city.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aap-catalog.get-stores\n      with:\n        zip: tools.zip\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: lookup-vehicle-makes\n      description: Get available vehicle makes for a given model year for fitment-based part search.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aap-catalog.list-vehicle-makes\n      with:\n        year: tools.year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-vehicle-models\n      description: Get available vehicle models for a year and make for fitment-based part search.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aap-catalog.list-vehicle-models\n      with:\n        year: tools.year\n        makeId: tools.makeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-years\n      description: Get the range of supported vehicle model years for parts catalog lookups.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aap-catalog.list-vehicle-years\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/advance-auto-parts/refs/heads/main/capabilities/auto-parts-shopping.yaml
tags:
- Advance Auto Parts
- Automotive
- E-Commerce
- Parts Catalog
- Loyalty
tools:
- description: Search for automotive parts by keyword, part number, or vehicle year/make/model.
  hints:
    openWorld: true
    readOnly: true
  name: search-auto-parts
- description: Get full specifications, fitment notes, and pricing for a specific automotive part.
  hints:
    openWorld: false
    readOnly: true
  name: get-part-details
- description: Check if an automotive part is in stock at nearby Advance Auto Parts stores.
  hints:
    openWorld: true
    readOnly: true
  name: check-part-availability
- description: Find Advance Auto Parts store locations near a ZIP code or city.
  hints:
    openWorld: true
    readOnly: true
  name: find-nearby-stores
- description: Get available vehicle makes for a given model year for fitment-based part search.
  hints:
    openWorld: true
    readOnly: true
  name: lookup-vehicle-makes
- description: Get available vehicle models for a year and make for fitment-based part search.
  hints:
    openWorld: true
    readOnly: true
  name: lookup-vehicle-models
- description: Get the range of supported vehicle model years for parts catalog lookups.
  hints:
    openWorld: true
    readOnly: true
  name: get-vehicle-years
---
