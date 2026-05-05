---
categories: []
consumed_apis:
- eikon-rdp
description: Unified workflow capability for financial analysts researching instruments, retrieving pricing data, ESG scores, news, and symbology from the Refinitiv Eikon Data Platform. Combines the Data Platform API for real-time and historical data with symbology concordance and instrument search.
layout: capability
name: Refinitiv Eikon Financial Data Research
operations:
- description: Retrieve historical interday pricing summaries.
  method: GET
  name: get-interday-pricing
  path: /v1/pricing/interday/{universe}
- description: Retrieve historical intraday pricing summaries.
  method: GET
  name: get-intraday-pricing
  path: /v1/pricing/intraday/{universe}
- description: Retrieve current pricing snapshots.
  method: GET
  name: get-pricing-snapshots
  path: /v1/pricing/snapshots/{universe}
- description: Retrieve financial news headlines.
  method: GET
  name: get-news-headlines
  path: /v1/news/headlines
- description: Retrieve a full news story.
  method: GET
  name: get-news-story
  path: /v1/news/stories/{storyId}
- description: Retrieve ESG scores.
  method: GET
  name: get-esg-scores
  path: /v1/esg/scores
- description: Retrieve detailed ESG measures.
  method: GET
  name: get-esg-measures
  path: /v1/esg/measures
- description: Map between instrument identifier types.
  method: POST
  name: lookup-symbology
  path: /v1/symbology/lookup
- description: Search for instruments and organizations.
  method: POST
  name: search-instruments
  path: /v1/search/instruments
personas: []
provider_name: Refinitiv Eikon
provider_slug: refinitiv-eikon
search_terms:
- news
- retrieve historical interday pricing summaries.
- retrieve esg scores.
- market data
- retrieve detailed esg measures and underlying data points for instruments.
- research
- esg scores for instruments.
- search across instruments, organizations, and economic indicators on the refinitiv data platform.
- symbology
- get interday pricing
- get news headlines
- get esg scores
- search and retrieve financial news headlines from reuters and other sources.
- retrieve historical intraday pricing at minute or hourly intervals.
- analytics
- financial data
- map between instrument identifier types.
- financial news
- get pricing snapshot
- real-time data
- map between different instrument identifier types (isin, cusip, sedol, ric, permid).
- retrieve historical intraday pricing summaries.
- retrieve historical interday pricing data for a financial instrument using its ric code.
- full news story content.
- financial news headlines.
- lookup symbology
- retrieve the full content of a financial news story by its story id.
- get news story
- esg
- historical interday pricing data for an instrument.
- real-time pricing snapshots.
- retrieve current pricing snapshots.
- get esg measures
- search instruments
- trading
- get pricing snapshots
- refinitiv eikon
- search for instruments and organizations.
- retrieve a full news story.
- instrument and entity search.
- detailed esg measures.
- get current real-time or delayed pricing snapshot for one or more instruments.
- retrieve detailed esg measures.
- instrument identifier concordance.
- historical intraday pricing data.
- get intraday pricing
- retrieve esg (environmental, social, governance) scores for financial instruments.
- retrieve financial news headlines.
slug: financial-data-research
source_filename: financial-data-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Refinitiv Eikon Financial Data Research\"\n  description: >-\n    Unified workflow capability for financial analysts researching instruments,\n    retrieving pricing data, ESG scores, news, and symbology from the Refinitiv\n    Eikon Data Platform. Combines the Data Platform API for real-time and\n    historical data with symbology concordance and instrument search.\n  tags:\n    - Refinitiv Eikon\n    - Financial Data\n    - Market Data\n    - ESG\n    - News\n    - Symbology\n    - Research\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REFINITIV_EIKON_ACCESS_TOKEN: REFINITIV_EIKON_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: eikon-rdp\n      location: ./shared/data-platform.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: eikon-research-api\n      description: \"Unified REST API for Refinitiv Eikon financial data research.\"\n      resources:\n\
  \        - path: /v1/pricing/interday/{universe}\n          name: interday-pricing\n          description: \"Historical interday pricing data for an instrument.\"\n          operations:\n            - method: GET\n              name: get-interday-pricing\n              description: \"Retrieve historical interday pricing summaries.\"\n              call: \"eikon-rdp.get-interday-summaries\"\n              with:\n                universe: \"rest.universe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pricing/intraday/{universe}\n          name: intraday-pricing\n          description: \"Historical intraday pricing data.\"\n          operations:\n            - method: GET\n              name: get-intraday-pricing\n              description: \"Retrieve historical intraday pricing summaries.\"\n              call: \"eikon-rdp.get-intraday-summaries\"\n              with:\n                universe: \"rest.universe\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pricing/snapshots/{universe}\n          name: pricing-snapshots\n          description: \"Real-time pricing snapshots.\"\n          operations:\n            - method: GET\n              name: get-pricing-snapshots\n              description: \"Retrieve current pricing snapshots.\"\n              call: \"eikon-rdp.get-pricing-snapshots\"\n              with:\n                universe: \"rest.universe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/news/headlines\n          name: news-headlines\n          description: \"Financial news headlines.\"\n          operations:\n            - method: GET\n              name: get-news-headlines\n              description: \"Retrieve financial news headlines.\"\n              call: \"eikon-rdp.get-news-headlines\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/news/stories/{storyId}\n          name: news-story\n          description: \"Full news story content.\"\n          operations:\n            - method: GET\n              name: get-news-story\n              description: \"Retrieve a full news story.\"\n              call: \"eikon-rdp.get-news-story\"\n              with:\n                storyId: \"rest.storyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/esg/scores\n          name: esg-scores\n          description: \"ESG scores for instruments.\"\n          operations:\n            - method: GET\n              name: get-esg-scores\n              description: \"Retrieve ESG scores.\"\n              call: \"eikon-rdp.get-esg-scores\"\n              with:\n                universe: \"rest.universe\"\n              outputParameters:\n                - type: object\n       \
  \           mapping: \"$.\"\n\n        - path: /v1/esg/measures\n          name: esg-measures\n          description: \"Detailed ESG measures.\"\n          operations:\n            - method: GET\n              name: get-esg-measures\n              description: \"Retrieve detailed ESG measures.\"\n              call: \"eikon-rdp.get-esg-measures\"\n              with:\n                universe: \"rest.universe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/symbology/lookup\n          name: symbology\n          description: \"Instrument identifier concordance.\"\n          operations:\n            - method: POST\n              name: lookup-symbology\n              description: \"Map between instrument identifier types.\"\n              call: \"eikon-rdp.lookup-symbology\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search/instruments\n\
  \          name: instrument-search\n          description: \"Instrument and entity search.\"\n          operations:\n            - method: POST\n              name: search-instruments\n              description: \"Search for instruments and organizations.\"\n              call: \"eikon-rdp.search-instruments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: eikon-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Refinitiv Eikon financial data research.\"\n      tools:\n        - name: get-interday-pricing\n          description: \"Retrieve historical interday pricing data for a financial instrument using its RIC code.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-rdp.get-interday-summaries\"\n          with:\n            universe: \"tools.universe\"\n          outputParameters:\n          \
  \  - type: object\n              mapping: \"$.\"\n\n        - name: get-intraday-pricing\n          description: \"Retrieve historical intraday pricing at minute or hourly intervals.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-rdp.get-intraday-summaries\"\n          with:\n            universe: \"tools.universe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-pricing-snapshot\n          description: \"Get current real-time or delayed pricing snapshot for one or more instruments.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-rdp.get-pricing-snapshots\"\n          with:\n            universe: \"tools.universe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-news-headlines\n          description: \"Search and retrieve financial news headlines from Reuters\
  \ and other sources.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"eikon-rdp.get-news-headlines\"\n          with:\n            query: \"tools.query\"\n            count: \"tools.count\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-news-story\n          description: \"Retrieve the full content of a financial news story by its story ID.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-rdp.get-news-story\"\n          with:\n            storyId: \"tools.storyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-esg-scores\n          description: \"Retrieve ESG (Environmental, Social, Governance) scores for financial instruments.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-rdp.get-esg-scores\"\n        \
  \  with:\n            universe: \"tools.universe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-esg-measures\n          description: \"Retrieve detailed ESG measures and underlying data points for instruments.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-rdp.get-esg-measures\"\n          with:\n            universe: \"tools.universe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: lookup-symbology\n          description: \"Map between different instrument identifier types (ISIN, CUSIP, SEDOL, RIC, PermID).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-rdp.lookup-symbology\"\n          with:\n            universe: \"tools.universe\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-instruments\n\
  \          description: \"Search across instruments, organizations, and economic indicators on the Refinitiv Data Platform.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"eikon-rdp.search-instruments\"\n          with:\n            query: \"tools.query\"\n            view: \"tools.view\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/refinitiv-eikon/refs/heads/main/capabilities/financial-data-research.yaml
tags:
- Refinitiv Eikon
- Financial Data
- Market Data
- ESG
- News
- Symbology
- Research
tools:
- description: Retrieve historical interday pricing data for a financial instrument using its RIC code.
  hints:
    openWorld: false
    readOnly: true
  name: get-interday-pricing
- description: Retrieve historical intraday pricing at minute or hourly intervals.
  hints:
    openWorld: false
    readOnly: true
  name: get-intraday-pricing
- description: Get current real-time or delayed pricing snapshot for one or more instruments.
  hints:
    openWorld: false
    readOnly: true
  name: get-pricing-snapshot
- description: Search and retrieve financial news headlines from Reuters and other sources.
  hints:
    openWorld: true
    readOnly: true
  name: get-news-headlines
- description: Retrieve the full content of a financial news story by its story ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-news-story
- description: Retrieve ESG (Environmental, Social, Governance) scores for financial instruments.
  hints:
    openWorld: false
    readOnly: true
  name: get-esg-scores
- description: Retrieve detailed ESG measures and underlying data points for instruments.
  hints:
    openWorld: false
    readOnly: true
  name: get-esg-measures
- description: Map between different instrument identifier types (ISIN, CUSIP, SEDOL, RIC, PermID).
  hints:
    openWorld: false
    readOnly: true
  name: lookup-symbology
- description: Search across instruments, organizations, and economic indicators on the Refinitiv Data Platform.
  hints:
    openWorld: true
    readOnly: true
  name: search-instruments
---
