---
categories: []
consumed_apis: []
description: The Archer Daniels Midland (ADM) Commodity Data API provides access to agricultural commodity pricing, supply chain logistics, and product information for ADM partner integrations. ADM is a Fortune 100 global leader in agricultural processing and food ingredient manufacturing.
layout: capability
name: Archer Daniels Midland Commodity Data API
operations:
- description: Archer Daniels Midland List Commodities
  method: GET
  name: listcommodities
  path: /commodities
- description: Archer Daniels Midland Get Commodity
  method: GET
  name: getcommodity
  path: /commodities/{commodityId}
- description: Archer Daniels Midland List Products
  method: GET
  name: listproducts
  path: /products
- description: Archer Daniels Midland List Locations
  method: GET
  name: listlocations
  path: /locations
personas: []
provider_name: Archer Daniels Midland
provider_slug: archer-daniels-midland
search_terms:
- nutrition
- worldwide processing facilities and logistics network
- procurement and supply chain managers sourcing agricultural inputs
- agricultural commodity traders tracking prices and market trends
- product developers sourcing food ingredients from adm
- commodities
- listcommodities
- archer daniels midland list locations
- daniels
- supply chain
- archer
- listproducts
- api
- archer daniels midland list commodities
- getcommodity
- food processing
- listlocations
- grain and oilseed commodity pricing and market data
- archer daniels midland list products
- processed food ingredient catalog and specifications
- archer daniels midland get commodity
- midland
- agriculture
- fortune 100
slug: archer-daniels-midland-capability
source_filename: archer-daniels-midland-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Archer Daniels Midland Commodity Data API\n  description: The Archer Daniels Midland (ADM) Commodity Data API provides access to agricultural commodity pricing, supply\n    chain logistics, and product information for ADM partner integrations. ADM is a Fortune 100 global leader in agricultural\n    processing and food ingredient manufacturing.\n  tags:\n  - Archer\n  - Daniels\n  - Midland\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: archer-daniels-midland\n    baseUri: https://api.adm.com/v1\n    description: Archer Daniels Midland Commodity Data API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-ADM-API-Key\n      value: '{{ARCHER_DANIELS_MIDLAND_TOKEN}}'\n    resources:\n    - name: commodities\n      path: /commodities\n      operations:\n      - name: listcommodities\n        method: GET\n        description: Archer Daniels\
  \ Midland List Commodities\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          description: Filter by commodity type (corn, soybeans, wheat, canola, etc.)\n        - name: region\n          in: query\n          type: string\n          description: Filter by sourcing region\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commodities-commodityid\n      path: /commodities/{commodityId}\n      operations:\n      - name: getcommodity\n        method: GET\n        description: Archer Daniels Midland Get Commodity\n        inputParameters:\n        - name: commodityId\n          in: path\n          type: string\n          required: true\n          description: Commodity identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n\
  \      operations:\n      - name: listproducts\n        method: GET\n        description: Archer Daniels Midland List Products\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          description: Filter by product category\n        - name: application\n          in: query\n          type: string\n          description: Filter by application area\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /locations\n      operations:\n      - name: listlocations\n        method: GET\n        description: Archer Daniels Midland List Locations\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          description: Filter by country code (ISO 3166-1 alpha-2)\n        - name: type\n          in: query\n          type: string\n          description: Filter by facility type\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: archer-daniels-midland-rest\n    description: REST adapter for Archer Daniels Midland Commodity Data API.\n    resources:\n    - path: /commodities\n      name: listcommodities\n      operations:\n      - method: GET\n        name: listcommodities\n        description: Archer Daniels Midland List Commodities\n        call: archer-daniels-midland.listcommodities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /commodities/{commodityId}\n      name: getcommodity\n      operations:\n      - method: GET\n        name: getcommodity\n        description: Archer Daniels Midland Get Commodity\n        call: archer-daniels-midland.getcommodity\n        with:\n          commodityId: rest.commodityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products\n\
  \      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n        description: Archer Daniels Midland List Products\n        call: archer-daniels-midland.listproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /locations\n      name: listlocations\n      operations:\n      - method: GET\n        name: listlocations\n        description: Archer Daniels Midland List Locations\n        call: archer-daniels-midland.listlocations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: archer-daniels-midland-mcp\n    transport: http\n    description: MCP adapter for Archer Daniels Midland Commodity Data API for AI agent use.\n    tools:\n    - name: listcommodities\n      description: Archer Daniels Midland List Commodities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archer-daniels-midland.listcommodities\n\
  \      with:\n        type: tools.type\n        region: tools.region\n      inputParameters:\n      - name: type\n        type: string\n        description: Filter by commodity type (corn, soybeans, wheat, canola, etc.)\n      - name: region\n        type: string\n        description: Filter by sourcing region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcommodity\n      description: Archer Daniels Midland Get Commodity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archer-daniels-midland.getcommodity\n      with:\n        commodityId: tools.commodityId\n      inputParameters:\n      - name: commodityId\n        type: string\n        description: Commodity identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproducts\n      description: Archer Daniels Midland List Products\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: archer-daniels-midland.listproducts\n      with:\n        category: tools.category\n        application: tools.application\n      inputParameters:\n      - name: category\n        type: string\n        description: Filter by product category\n      - name: application\n        type: string\n        description: Filter by application area\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlocations\n      description: Archer Daniels Midland List Locations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archer-daniels-midland.listlocations\n      with:\n        country: tools.country\n        type: tools.type\n      inputParameters:\n      - name: country\n        type: string\n        description: Filter by country code (ISO 3166-1 alpha-2)\n      - name: type\n        type: string\n        description: Filter by facility type\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ARCHER_DANIELS_MIDLAND_TOKEN: ARCHER_DANIELS_MIDLAND_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/archer-daniels-midland/refs/heads/main/capabilities/archer-daniels-midland-capability.yaml
tags:
- Archer
- Daniels
- Midland
- API
tools:
- description: Archer Daniels Midland List Commodities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcommodities
- description: Archer Daniels Midland Get Commodity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcommodity
- description: Archer Daniels Midland List Products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
- description: Archer Daniels Midland List Locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocations
---
