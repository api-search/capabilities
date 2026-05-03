---
categories: []
consumed_apis:
- refinitiv-rdp
description: Unified workflow capability for financial analysts and quants accessing pricing data, ESG scores, news, and instrument search through the Refinitiv Data Platform. Combines historical and real-time pricing with ESG analytics, news, and symbology concordance.
layout: capability
name: Refinitiv Financial Market Data
operations:
- description: Historical interday pricing summaries.
  method: GET
  name: get-interday-pricing
  path: /v1/pricing/interday/{universe}
- description: Historical intraday pricing summaries.
  method: GET
  name: get-intraday-pricing
  path: /v1/pricing/intraday/{universe}
- description: Real-time pricing snapshots.
  method: GET
  name: get-pricing-snapshots
  path: /v1/pricing/snapshots/{universe}
- description: Financial news headlines.
  method: GET
  name: get-news-headlines
  path: /v1/news/headlines
- description: ESG scores for instruments.
  method: GET
  name: get-esg-scores
  path: /v1/esg/scores
- description: Detailed ESG measures.
  method: GET
  name: get-esg-measures
  path: /v1/esg/measures
- description: Convert between identifier types.
  method: POST
  name: convert-symbology
  path: /v1/symbology/convert
- description: Search for instruments.
  method: POST
  name: search-instruments
  path: /v1/search/instruments
personas: []
provider_name: Refinitiv
provider_slug: refinitiv
search_terms:
- esg scores for instruments.
- convert between identifier types.
- search for instruments, organizations, and economic indicators.
- get intraday pricing
- analytics
- real-time pricing snapshots.
- get esg scores
- get news headlines
- financial news headlines.
- market data
- get current real-time or delayed pricing snapshot for one or more instruments.
- retrieve historical daily/weekly/monthly ohlcv pricing for a financial instrument by ric.
- refinitiv
- search instruments
- detailed esg measures.
- esg
- news
- convert instrument identifiers between isin, cusip, sedol, ric, and permid.
- convert symbology
- get pricing snapshot
- search and retrieve financial news from reuters and other sources.
- get pricing snapshots
- financial data
- get esg measures
- historical intraday pricing summaries.
- get interday pricing
- search for instruments.
- retrieve historical intraday pricing at 1, 5, 30, or 60 minute intervals.
- historical interday pricing summaries.
- retrieve esg pillar scores for financial instruments.
slug: financial-market-data
source_filename: financial-market-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Refinitiv Financial Market Data\"\n  description: >-\n    Unified workflow capability for financial analysts and quants accessing\n    pricing data, ESG scores, news, and instrument search through the Refinitiv\n    Data Platform. Combines historical and real-time pricing with ESG analytics,\n    news, and symbology concordance.\n  tags:\n    - Refinitiv\n    - Financial Data\n    - Market Data\n    - ESG\n    - News\n    - Analytics\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RDP_ACCESS_TOKEN: RDP_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: refinitiv-rdp\n      location: ./shared/data-platform.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: refinitiv-market-data-api\n      description: \"Unified REST API for Refinitiv financial market data.\"\n      resources:\n        - path: /v1/pricing/interday/{universe}\n          name: interday-pricing\n\
  \          operations:\n            - method: GET\n              name: get-interday-pricing\n              description: \"Historical interday pricing summaries.\"\n              call: \"refinitiv-rdp.get-interday-pricing\"\n              with:\n                universe: \"rest.universe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pricing/intraday/{universe}\n          name: intraday-pricing\n          operations:\n            - method: GET\n              name: get-intraday-pricing\n              description: \"Historical intraday pricing summaries.\"\n              call: \"refinitiv-rdp.get-intraday-pricing\"\n              with:\n                universe: \"rest.universe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pricing/snapshots/{universe}\n          name: pricing-snapshots\n          operations:\n            - method: GET\n\
  \              name: get-pricing-snapshots\n              description: \"Real-time pricing snapshots.\"\n              call: \"refinitiv-rdp.get-pricing-snapshots\"\n              with:\n                universe: \"rest.universe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/news/headlines\n          name: news-headlines\n          operations:\n            - method: GET\n              name: get-news-headlines\n              description: \"Financial news headlines.\"\n              call: \"refinitiv-rdp.get-news-headlines\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/esg/scores\n          name: esg-scores\n          operations:\n            - method: GET\n              name: get-esg-scores\n              description: \"ESG scores for instruments.\"\n              call: \"refinitiv-rdp.get-esg-scores\"\n              with:\n        \
  \        universe: \"rest.universe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/esg/measures\n          name: esg-measures\n          operations:\n            - method: GET\n              name: get-esg-measures\n              description: \"Detailed ESG measures.\"\n              call: \"refinitiv-rdp.get-esg-measures\"\n              with:\n                universe: \"rest.universe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/symbology/convert\n          name: symbology\n          operations:\n            - method: POST\n              name: convert-symbology\n              description: \"Convert between identifier types.\"\n              call: \"refinitiv-rdp.convert-symbology\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search/instruments\n       \
  \   name: instrument-search\n          operations:\n            - method: POST\n              name: search-instruments\n              description: \"Search for instruments.\"\n              call: \"refinitiv-rdp.search-instruments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: refinitiv-market-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Refinitiv financial data access.\"\n      tools:\n        - name: get-interday-pricing\n          description: \"Retrieve historical daily/weekly/monthly OHLCV pricing for a financial instrument by RIC.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"refinitiv-rdp.get-interday-pricing\"\n          with:\n            universe: \"tools.universe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-intraday-pricing\n\
  \          description: \"Retrieve historical intraday pricing at 1, 5, 30, or 60 minute intervals.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"refinitiv-rdp.get-intraday-pricing\"\n          with:\n            universe: \"tools.universe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pricing-snapshot\n          description: \"Get current real-time or delayed pricing snapshot for one or more instruments.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"refinitiv-rdp.get-pricing-snapshots\"\n          with:\n            universe: \"tools.universe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-news-headlines\n          description: \"Search and retrieve financial news from Reuters and other sources.\"\n          hints:\n            readOnly: true\n           \
  \ openWorld: true\n          call: \"refinitiv-rdp.get-news-headlines\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-esg-scores\n          description: \"Retrieve ESG pillar scores for financial instruments.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"refinitiv-rdp.get-esg-scores\"\n          with:\n            universe: \"tools.universe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: convert-symbology\n          description: \"Convert instrument identifiers between ISIN, CUSIP, SEDOL, RIC, and PermID.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"refinitiv-rdp.convert-symbology\"\n          with:\n            universe: \"tools.universe\"\n          outputParameters:\n            - type: object\n          \
  \    mapping: \"$.\"\n\n        - name: search-instruments\n          description: \"Search for instruments, organizations, and economic indicators.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"refinitiv-rdp.search-instruments\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/refinitiv/refs/heads/main/capabilities/financial-market-data.yaml
tags:
- Refinitiv
- Financial Data
- Market Data
- ESG
- News
- Analytics
tools:
- description: Retrieve historical daily/weekly/monthly OHLCV pricing for a financial instrument by RIC.
  hints:
    openWorld: false
    readOnly: true
  name: get-interday-pricing
- description: Retrieve historical intraday pricing at 1, 5, 30, or 60 minute intervals.
  hints:
    openWorld: false
    readOnly: true
  name: get-intraday-pricing
- description: Get current real-time or delayed pricing snapshot for one or more instruments.
  hints:
    openWorld: false
    readOnly: true
  name: get-pricing-snapshot
- description: Search and retrieve financial news from Reuters and other sources.
  hints:
    openWorld: true
    readOnly: true
  name: get-news-headlines
- description: Retrieve ESG pillar scores for financial instruments.
  hints:
    openWorld: false
    readOnly: true
  name: get-esg-scores
- description: Convert instrument identifiers between ISIN, CUSIP, SEDOL, RIC, and PermID.
  hints:
    openWorld: false
    readOnly: true
  name: convert-symbology
- description: Search for instruments, organizations, and economic indicators.
  hints:
    openWorld: true
    readOnly: true
  name: search-instruments
---
