---
categories: []
consumed_apis:
- aap-catalog
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
- fleet operations manager ordering parts for vehicle maintenance programs
- automotive technician
- supply chain
- retail
- get vehicle years
- get available vehicle makes for a given model year for fitment-based part search.
- advance auto parts
- search auto parts
- lookup vehicle makes
- e-commerce
- find nearby stores
- unified workflow for automotive parts discovery, fitment lookup, inventory, and ordering
- parts catalog
- get available vehicle models for a year and make for fitment-based part search.
- do-it-yourself automotive enthusiast sourcing parts for self-repairs
- get part details
- check part inventory at stores.
- find advance auto parts store locations near a zip code or city.
- check if an automotive part is in stock at nearby advance auto parts stores.
- get full specifications, fitment notes, and pricing for a specific automotive part.
- part details.
- automotive
- check part availability
- get part
- store inventory.
- fleet manager
- get the range of supported vehicle model years for parts catalog lookups.
- search for automotive parts by keyword, part number, or vehicle year/make/model.
- professional mechanic using the api to source parts for repair jobs
- check inventory
- loyalty
- get automotive part details.
- search for automotive parts.
- parts catalog search.
- diy customer
- lookup vehicle models
- search parts
slug: auto-parts-shopping
source_filename: auto-parts-shopping.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Advance Auto Parts Shopping\"\n  description: \"Unified workflow capability for automotive parts discovery, fitment lookup, inventory checking, ordering, and loyalty management. Designed for automotive technicians, fleet managers, and DIY customers.\"\n  tags:\n    - Advance Auto Parts\n    - Automotive\n    - E-Commerce\n    - Parts Catalog\n    - Loyalty\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AAP_API_KEY: AAP_API_KEY\n      AAP_OAUTH_TOKEN: AAP_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: aap-catalog\n      location: ./shared/catalog-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8090\n      namespace: aap-shopping-api\n      description: \"Unified REST API for Advance Auto Parts catalog search, inventory, ordering, and loyalty.\"\n      resources:\n        - path: /v1/parts\n          name: parts\n          description: \"Parts catalog search.\"\
  \n          operations:\n            - method: GET\n              name: search-parts\n              description: \"Search for automotive parts.\"\n              call: \"aap-catalog.search-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/parts/{productId}\n          name: part\n          description: \"Part details.\"\n          operations:\n            - method: GET\n              name: get-part\n              description: \"Get automotive part details.\"\n              call: \"aap-catalog.get-product\"\n              with:\n                productId: \"rest.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/inventory\n          name: inventory\n          description: \"Store inventory.\"\n          operations:\n            - method: GET\n              name: check-inventory\n              description: \"Check part inventory\
  \ at stores.\"\n              call: \"aap-catalog.check-inventory\"\n              with:\n                productId: \"rest.productId\"\n                zip: \"rest.zip\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: aap-shopping-mcp\n      transport: http\n      description: \"MCP server for AI-assisted automotive parts shopping — find parts, check availability, and manage orders.\"\n      tools:\n        - name: search-auto-parts\n          description: \"Search for automotive parts by keyword, part number, or vehicle year/make/model.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aap-catalog.search-products\"\n          with:\n            q: \"tools.q\"\n            year: \"tools.year\"\n            makeId: \"tools.makeId\"\n            modelId: \"tools.modelId\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n        - name: get-part-details\n          description: \"Get full specifications, fitment notes, and pricing for a specific automotive part.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aap-catalog.get-product\"\n          with:\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-part-availability\n          description: \"Check if an automotive part is in stock at nearby Advance Auto Parts stores.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aap-catalog.check-inventory\"\n          with:\n            productId: \"tools.productId\"\n            zip: \"tools.zip\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-nearby-stores\n          description: \"Find Advance Auto Parts store locations near a\
  \ ZIP code or city.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aap-catalog.get-stores\"\n          with:\n            zip: \"tools.zip\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-vehicle-makes\n          description: \"Get available vehicle makes for a given model year for fitment-based part search.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aap-catalog.list-vehicle-makes\"\n          with:\n            year: \"tools.year\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-vehicle-models\n          description: \"Get available vehicle models for a year and make for fitment-based part search.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aap-catalog.list-vehicle-models\"\n          with:\n            year:\
  \ \"tools.year\"\n            makeId: \"tools.makeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-years\n          description: \"Get the range of supported vehicle model years for parts catalog lookups.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aap-catalog.list-vehicle-years\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
