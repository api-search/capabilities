---
categories: []
consumed_apis: []
description: Wine data capability for Wine-Searcher, enabling end-to-end wine price discovery, merchant comparisons, critic score lookups, and cellar valuation. Designed for wine apps, investment platforms, insurance tools, e-commerce integrations, and market research applications.
layout: capability
name: Wine-Searcher Wine Data
operations:
- description: Get aggregated wine data including price, score, and region
  method: GET
  name: get-wine-data
  path: /v1/wines
- description: Get merchant price listings for a wine
  method: GET
  name: get-wine-prices
  path: /v1/wines/{winename}/prices
personas: []
provider_name: Wine-Searcher
provider_slug: wine-searcher
search_terms:
- get merchant price listings for a wine
- wine
- get merchant listings and prices for a specific wine, sorted lowest price first
- data
- marketplace
- prices
- get wine prices
- vintages
- get aggregated wine data including price, score, and region
- wine data lookup by name
- look up a wine by name to get pricing, critic score, grape variety, and region data
- lookup wine
- market price listings for a specific wine
- get wine data
- wine searcher
- valuations
- merchants
- critics
slug: wine-data
source_filename: wine-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Wine-Searcher Wine Data\n  description: Wine data capability for Wine-Searcher, enabling end-to-end wine price discovery, merchant comparisons, critic\n    score lookups, and cellar valuation. Designed for wine apps, investment platforms, insurance tools, e-commerce integrations,\n    and market research applications.\n  tags:\n  - Wine Searcher\n  - Wine\n  - Prices\n  - Data\n  - Marketplace\n  - Merchants\n  - Valuations\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WINE_SEARCHER_API_KEY: WINE_SEARCHER_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: wine-searcher\n    baseUri: https://www.wine-searcher.com/ws_api.php\n    description: Wine-Searcher API for wine pricing and data\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{WINE_SEARCHER_API_KEY}}'\n      placement: query\n    resources:\n    - name: wine-check\n      path: /wine-check\n  \
  \    description: Wine price check and aggregated data\n      operations:\n      - name: get-wine-check\n        method: GET\n        description: Get Wine Check Data\n        inputParameters:\n        - name: api_key\n          in: query\n          type: string\n          required: true\n          description: API key for authentication\n        - name: winename\n          in: query\n          type: string\n          required: true\n          description: Wine name to look up\n        - name: vintage\n          in: query\n          type: string\n          required: false\n          description: Vintage year\n        - name: currencycode\n          in: query\n          type: string\n          required: false\n          description: Currency code\n        - name: location\n          in: query\n          type: string\n          required: false\n          description: Country filter\n        - name: offer_type\n          in: query\n          type: string\n          required: false\n     \
  \     description: Offer type filter (R/A/B)\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format (json/xml)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: market-price\n      path: /market-price\n      description: Merchant price listings\n      operations:\n      - name: get-market-price\n        method: GET\n        description: Get Market Price Listings\n        inputParameters:\n        - name: api_key\n          in: query\n          type: string\n          required: true\n          description: API key for authentication\n        - name: winename\n          in: query\n          type: string\n          required: true\n          description: Wine name to look up\n        - name: vintage\n          in: query\n          type: string\n          required: false\n          description: Vintage year\n        - name:\
  \ currencycode\n          in: query\n          type: string\n          required: false\n          description: Currency code\n        - name: location\n          in: query\n          type: string\n          required: false\n          description: Country filter\n        - name: offer_type\n          in: query\n          type: string\n          required: false\n          description: Offer type filter (R/A/B)\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format (json/xml)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wine-data-api\n    description: Unified REST API for Wine-Searcher wine data.\n    resources:\n    - path: /v1/wines\n      name: wines\n      description: Wine data lookup by name\n      operations:\n      - method: GET\n        name: get-wine-data\n  \
  \      description: Get aggregated wine data including price, score, and region\n        call: wine-searcher.get-wine-check\n        with:\n          winename: rest.winename\n          vintage: rest.vintage\n          currencycode: rest.currencycode\n          location: rest.location\n          offer_type: rest.offer_type\n          format: json\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/wines/{winename}/prices\n      name: wine-prices\n      description: Market price listings for a specific wine\n      operations:\n      - method: GET\n        name: get-wine-prices\n        description: Get merchant price listings for a wine\n        call: wine-searcher.get-market-price\n        with:\n          winename: rest.winename\n          vintage: rest.vintage\n          currencycode: rest.currencycode\n          location: rest.location\n          offer_type: rest.offer_type\n          format: json\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wine-data-mcp\n    transport: http\n    description: MCP server for AI-assisted wine data lookup and price comparison.\n    tools:\n    - name: lookup-wine\n      description: Look up a wine by name to get pricing, critic score, grape variety, and region data\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wine-searcher.get-wine-check\n      with:\n        winename: tools.winename\n        vintage: tools.vintage\n        currencycode: tools.currencycode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-wine-prices\n      description: Get merchant listings and prices for a specific wine, sorted lowest price first\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wine-searcher.get-market-price\n      with:\n        winename: tools.winename\n        vintage: tools.vintage\n        currencycode: tools.currencycode\n        location:\
  \ tools.location\n        offer_type: tools.offer_type\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wine-searcher/refs/heads/main/capabilities/wine-data.yaml
tags:
- Wine Searcher
- Wine
- Prices
- Data
- Marketplace
- Merchants
- Valuations
tools:
- description: Look up a wine by name to get pricing, critic score, grape variety, and region data
  hints:
    openWorld: true
    readOnly: true
  name: lookup-wine
- description: Get merchant listings and prices for a specific wine, sorted lowest price first
  hints:
    openWorld: true
    readOnly: true
  name: get-wine-prices
---
