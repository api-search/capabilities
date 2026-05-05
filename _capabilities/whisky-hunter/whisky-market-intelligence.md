---
categories: []
consumed_apis:
- whisky-hunter
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
- market data
- distilleries
- list all tracked distilleries with their slugs for further data queries.
- list all whisky distilleries tracked in the database. returns names and slugs that can be used with get-distillery-data to research specific distillery auction performance.
- collectors
- spirits
- get auctions data
- investors
- aggregated whisky auction statistics across all tracked platforms.
- get historical auction trading volumes and price statistics for a distillery.
- all distilleries tracked in the whisky hunter database.
- whisky
- list distilleries
- get historical whisky auction data for a specific distillery, including trading volumes, lot counts, and winning bid statistics over time. use the slug from list-distilleries (e.g., 'macallan', 'ardbeg', 'yamazaki').
- historical auction data for a specific distillery.
- get aggregated whisky auction statistics across all 28 tracked platforms including trading volumes, winning bid ranges, and lot counts. useful for understanding overall market activity and trends.
- get distillery data
- auctions
- price research
- get aggregated auction trading volumes, bid statistics, and lot counts across all 28 tracked platforms.
- market intelligence
slug: whisky-market-intelligence
source_filename: whisky-market-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Whisky Market Intelligence\"\n  description: >-\n    Unified whisky market intelligence capability composing auction data and distillery\n    analytics from the Whisky Hunter API to support collectors, investors, and traders\n    researching whisky market trends, distillery performance, and auction price dynamics.\n  tags:\n    - Whisky\n    - Market Intelligence\n    - Auctions\n    - Distilleries\n    - Collectors\n    - Investors\n    - Price Research\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\ncapability:\n  consumes:\n    - import: whisky-hunter\n      location: ./shared/whisky-hunter-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: whisky-market-intelligence-api\n      description: \"Unified REST API for whisky market research, auction analytics, and distillery price tracking.\"\n      resources:\n        - path: /v1/auctions\n          name: auctions\n          description: \"Aggregated\
  \ whisky auction statistics across all tracked platforms.\"\n          operations:\n            - method: GET\n              name: get-auctions-data\n              description: \"Get aggregated auction trading volumes, bid statistics, and lot counts across all 28 tracked platforms.\"\n              call: \"whisky-hunter.get-auctions-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/distilleries\n          name: distilleries\n          description: \"All distilleries tracked in the Whisky Hunter database.\"\n          operations:\n            - method: GET\n              name: list-distilleries\n              description: \"List all tracked distilleries with their slugs for further data queries.\"\n              call: \"whisky-hunter.list-distilleries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/distilleries/{slug}\n          name:\
  \ distillery-auction-data\n          description: \"Historical auction data for a specific distillery.\"\n          operations:\n            - method: GET\n              name: get-distillery-data\n              description: \"Get historical auction trading volumes and price statistics for a distillery.\"\n              call: \"whisky-hunter.get-distillery-data\"\n              with:\n                slug: \"rest.slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: whisky-market-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted whisky market research and investment analysis.\"\n      tools:\n        - name: get-auctions-data\n          description: >-\n            Get aggregated whisky auction statistics across all 28 tracked platforms\n            including trading volumes, winning bid ranges, and lot counts. Useful for\n            understanding\
  \ overall market activity and trends.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"whisky-hunter.get-auctions-data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-distilleries\n          description: >-\n            List all whisky distilleries tracked in the database. Returns names and\n            slugs that can be used with get-distillery-data to research specific\n            distillery auction performance.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"whisky-hunter.list-distilleries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-distillery-data\n          description: >-\n            Get historical whisky auction data for a specific distillery, including\n            trading volumes, lot counts, and winning bid statistics over time.\n            Use the slug\
  \ from list-distilleries (e.g., 'macallan', 'ardbeg', 'yamazaki').\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"whisky-hunter.get-distillery-data\"\n          with:\n            slug: \"tools.slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
