---
categories: []
consumed_apis: []
description: Unified whisky market intelligence capability composing auction data and distillery analytics from the Whisky Hunter API to support collectors, investors, and traders researching whisky market trends, distillery performance, and auction price dynamics.
layout: capability
name: Whisky Market Intelligence
operations:
- description: Get aggregated auction trading volumes, bid statistics, and lot counts across all 28 tracked platforms.
  method: GET
  name: get-auctions-data
  path: /v1/auctions
- description: List all tracked distilleries with their slugs for further data queries.
  method: GET
  name: list-distilleries
  path: /v1/distilleries
- description: Get historical auction trading volumes and price statistics for a distillery.
  method: GET
  name: get-distillery-data
  path: /v1/distilleries/{slug}
personas: []
provider_name: Whisky Hunter
provider_slug: whisky-hunter
search_terms:
- aggregated whisky auction statistics across all tracked platforms.
- get historical whisky auction data for a specific distillery, including trading volumes, lot counts, and winning bid statistics over time. use the slug from list-distilleries (e.g., 'macallan', 'ardbeg', 'yamazaki').
- price research
- historical auction data for a specific distillery.
- all distilleries tracked in the whisky hunter database.
- collectors
- distilleries
- get aggregated whisky auction statistics across all 28 tracked platforms including trading volumes, winning bid ranges, and lot counts. useful for understanding overall market activity and trends.
- market intelligence
- list all whisky distilleries tracked in the database. returns names and slugs that can be used with get-distillery-data to research specific distillery auction performance.
- whisky
- spirits
- get auctions data
- investors
- list distilleries
- auctions
- market data
- list all tracked distilleries with their slugs for further data queries.
- get distillery data
- get historical auction trading volumes and price statistics for a distillery.
- get aggregated auction trading volumes, bid statistics, and lot counts across all 28 tracked platforms.
slug: whisky-market-intelligence
source_filename: whisky-market-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Whisky Market Intelligence\n  description: Unified whisky market intelligence capability composing auction data and distillery analytics from the Whisky\n    Hunter API to support collectors, investors, and traders researching whisky market trends, distillery performance, and\n    auction price dynamics.\n  tags:\n  - Whisky\n  - Market Intelligence\n  - Auctions\n  - Distilleries\n  - Collectors\n  - Investors\n  - Price Research\n  created: '2026-05-03'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: whisky-hunter\n    baseUri: https://whiskyhunter.net/api\n    description: Whisky Hunter public API for whisky auction market data.\n    resources:\n    - name: auctions-data\n      path: /auctions_data/\n      description: Aggregated auction data across all tracked platforms.\n      operations:\n      - name: get-auctions-data\n        method: GET\n        description: Returns aggregated auction statistics\
  \ across all 28 tracked whisky auction platforms.\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format (json).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: distilleries-info\n      path: /distilleries_info/\n      description: List of all tracked distilleries with their slugs.\n      operations:\n      - name: list-distilleries\n        method: GET\n        description: Returns all distilleries tracked in the Whisky Hunter database.\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: distillery-data\n      path: /distillery_data/{slug}/\n      description: Historical auction data\
  \ for a specific distillery.\n      operations:\n      - name: get-distillery-data\n        method: GET\n        description: Returns historical auction data for the specified distillery.\n        inputParameters:\n        - name: slug\n          in: path\n          type: string\n          required: true\n          description: Distillery URL slug from the distilleries endpoint.\n        - name: format\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: whisky-market-intelligence-api\n    description: Unified REST API for whisky market research, auction analytics, and distillery price tracking.\n    resources:\n    - path: /v1/auctions\n      name: auctions\n      description: Aggregated whisky auction statistics across all tracked platforms.\n      operations:\n      - method: GET\n\
  \        name: get-auctions-data\n        description: Get aggregated auction trading volumes, bid statistics, and lot counts across all 28 tracked platforms.\n        call: whisky-hunter.get-auctions-data\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/distilleries\n      name: distilleries\n      description: All distilleries tracked in the Whisky Hunter database.\n      operations:\n      - method: GET\n        name: list-distilleries\n        description: List all tracked distilleries with their slugs for further data queries.\n        call: whisky-hunter.list-distilleries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/distilleries/{slug}\n      name: distillery-auction-data\n      description: Historical auction data for a specific distillery.\n      operations:\n      - method: GET\n        name: get-distillery-data\n        description: Get historical auction trading volumes and price statistics\
  \ for a distillery.\n        call: whisky-hunter.get-distillery-data\n        with:\n          slug: rest.slug\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: whisky-market-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted whisky market research and investment analysis.\n    tools:\n    - name: get-auctions-data\n      description: Get aggregated whisky auction statistics across all 28 tracked platforms including trading volumes, winning\n        bid ranges, and lot counts. Useful for understanding overall market activity and trends.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whisky-hunter.get-auctions-data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-distilleries\n      description: List all whisky distilleries tracked in the database. Returns names and slugs that can be used with get-distillery-data\n     \
  \   to research specific distillery auction performance.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whisky-hunter.list-distilleries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-distillery-data\n      description: Get historical whisky auction data for a specific distillery, including trading volumes, lot counts, and\n        winning bid statistics over time. Use the slug from list-distilleries (e.g., 'macallan', 'ardbeg', 'yamazaki').\n      hints:\n        readOnly: true\n        openWorld: false\n      call: whisky-hunter.get-distillery-data\n      with:\n        slug: tools.slug\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/whisky-hunter/refs/heads/main/capabilities/whisky-market-intelligence.yaml
tags:
- Whisky
- Market Intelligence
- Auctions
- Distilleries
- Collectors
- Investors
- Price Research
tools:
- description: Get aggregated whisky auction statistics across all 28 tracked platforms including trading volumes, winning bid ranges, and lot counts. Useful for understanding overall market activity and trends.
  hints:
    openWorld: true
    readOnly: true
  name: get-auctions-data
- description: List all whisky distilleries tracked in the database. Returns names and slugs that can be used with get-distillery-data to research specific distillery auction performance.
  hints:
    openWorld: true
    readOnly: true
  name: list-distilleries
- description: Get historical whisky auction data for a specific distillery, including trading volumes, lot counts, and winning bid statistics over time. Use the slug from list-distilleries (e.g., 'macallan', 'ardbeg', 'yamazaki').
  hints:
    openWorld: false
    readOnly: true
  name: get-distillery-data
---
