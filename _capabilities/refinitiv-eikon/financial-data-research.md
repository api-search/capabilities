---
categories: []
consumed_apis: []
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
- analytics
- detailed esg measures.
- full news story content.
- search and retrieve financial news headlines from reuters and other sources.
- get pricing snapshot
- retrieve esg scores.
- instrument identifier concordance.
- retrieve a full news story.
- get current real-time or delayed pricing snapshot for one or more instruments.
- retrieve historical interday pricing summaries.
- retrieve detailed esg measures.
- lookup symbology
- refinitiv eikon
- retrieve detailed esg measures and underlying data points for instruments.
- retrieve historical interday pricing data for a financial instrument using its ric code.
- search instruments
- financial news headlines.
- research
- financial data
- retrieve historical intraday pricing summaries.
- retrieve historical intraday pricing at minute or hourly intervals.
- get intraday pricing
- trading
- get news headlines
- search across instruments, organizations, and economic indicators on the refinitiv data platform.
- get esg scores
- real-time pricing snapshots.
- search for instruments and organizations.
- get esg measures
- esg
- retrieve financial news headlines.
- symbology
- historical intraday pricing data.
- map between instrument identifier types.
- retrieve esg (environmental, social, governance) scores for financial instruments.
- retrieve current pricing snapshots.
- real-time data
- get news story
- financial news
- get interday pricing
- market data
- retrieve the full content of a financial news story by its story id.
- get pricing snapshots
- esg scores for instruments.
- map between different instrument identifier types (isin, cusip, sedol, ric, permid).
- historical interday pricing data for an instrument.
- news
- instrument and entity search.
slug: financial-data-research
source_filename: financial-data-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Refinitiv Eikon Financial Data Research\n  description: Unified workflow capability for financial analysts researching instruments, retrieving pricing data, ESG scores,\n    news, and symbology from the Refinitiv Eikon Data Platform. Combines the Data Platform API for real-time and historical\n    data with symbology concordance and instrument search.\n  tags:\n  - Refinitiv Eikon\n  - Financial Data\n  - Market Data\n  - ESG\n  - News\n  - Symbology\n  - Research\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REFINITIV_EIKON_ACCESS_TOKEN: REFINITIV_EIKON_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: eikon-rdp\n    baseUri: https://api.refinitiv.com\n    description: Refinitiv Data Platform RESTful API for financial data access.\n    authentication:\n      type: bearer\n      token: '{{REFINITIV_EIKON_ACCESS_TOKEN}}'\n    resources:\n    - name: authentication\n     \
  \ path: /auth/oauth2/v1/token\n      description: OAuth 2.0 token management.\n      operations:\n      - name: get-access-token\n        method: POST\n        description: Obtain an OAuth 2.0 access token.\n        inputParameters:\n        - name: grant_type\n          in: body\n          type: string\n          required: true\n          description: OAuth grant type (password or refresh_token).\n        - name: username\n          in: body\n          type: string\n          required: false\n          description: RDP username.\n        - name: password\n          in: body\n          type: string\n          required: false\n          description: RDP password.\n        - name: client_id\n          in: body\n          type: string\n          required: true\n          description: Application client identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historical-pricing\n      path: /data/historical-pricing/v1/views\n\
  \      description: Historical interday and intraday pricing data.\n      operations:\n      - name: get-interday-summaries\n        method: GET\n        description: Retrieve historical interday pricing summaries for an instrument.\n        inputParameters:\n        - name: universe\n          in: path\n          type: string\n          required: true\n          description: Instrument RIC identifier.\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start date in ISO 8601 format.\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End date in ISO 8601 format.\n        - name: interval\n          in: query\n          type: string\n          required: false\n          description: Time interval (P1D, P7D, P1M, P3M, P1Y).\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated\
  \ list of fields.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-intraday-summaries\n        method: GET\n        description: Retrieve historical intraday pricing summaries.\n        inputParameters:\n        - name: universe\n          in: path\n          type: string\n          required: true\n          description: Instrument RIC identifier.\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start date in ISO 8601 format.\n        - name: interval\n          in: query\n          type: string\n          required: false\n          description: Intraday interval (PT1M, PT5M, PT30M, PT60M).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: streaming-pricing\n      path: /data/pricing/snapshots/v1\n      description: Real-time and delayed\
  \ pricing snapshots.\n      operations:\n      - name: get-pricing-snapshots\n        method: GET\n        description: Retrieve current pricing snapshots for instruments.\n        inputParameters:\n        - name: universe\n          in: path\n          type: string\n          required: true\n          description: Comma-separated list of instrument RICs.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: news\n      path: /data/news/v1\n      description: Financial news headlines and stories.\n      operations:\n      - name: get-news-headlines\n        method: GET\n        description: Retrieve financial news headlines.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n     \
  \     description: Free-text search query.\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of headlines to return.\n        - name: dateFrom\n          in: query\n          type: string\n          required: false\n          description: Start date in ISO 8601 format.\n        - name: dateTo\n          in: query\n          type: string\n          required: false\n          description: End date in ISO 8601 format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-news-story\n        method: GET\n        description: Retrieve the full content of a news story.\n        inputParameters:\n        - name: storyId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the news story.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: esg\n      path: /data/environmental-social-governance/v2/views\n      description: ESG scores and measures.\n      operations:\n      - name: get-esg-scores\n        method: GET\n        description: Retrieve full ESG scores for instruments.\n        inputParameters:\n        - name: universe\n          in: query\n          type: string\n          required: true\n          description: Comma-separated instrument identifiers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-esg-measures\n        method: GET\n        description: Retrieve detailed ESG measures for instruments.\n        inputParameters:\n        - name: universe\n          in: query\n          type: string\n          required: true\n          description: Comma-separated instrument identifiers.\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: symbology\n      path: /discovery/symbology/v1\n      description: Instrument identifier concordance.\n      operations:\n      - name: lookup-symbology\n        method: POST\n        description: Map between different instrument identifier types.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            from: '{{tools.from}}'\n            to: '{{tools.to}}'\n            universe: '{{tools.universe}}'\n    - name: search\n      path: /discovery/search/v1/\n      description: Search across instruments, organizations, and indicators.\n      operations:\n      - name: search-instruments\n        method: POST\n        description: Search for instruments and organizations.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            View: '{{tools.view}}'\n            Query: '{{tools.query}}'\n            Filter: '{{tools.filter}}'\n            Top: '{{tools.top}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: eikon-research-api\n    description: Unified REST API for Refinitiv Eikon financial data research.\n    resources:\n    - path: /v1/pricing/interday/{universe}\n      name: interday-pricing\n      description: Historical interday pricing data for an instrument.\n      operations:\n      - method: GET\n        name: get-interday-pricing\n        description: Retrieve historical interday pricing summaries.\n        call: eikon-rdp.get-interday-summaries\n        with:\n          universe: rest.universe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pricing/intraday/{universe}\n      name: intraday-pricing\n      description:\
  \ Historical intraday pricing data.\n      operations:\n      - method: GET\n        name: get-intraday-pricing\n        description: Retrieve historical intraday pricing summaries.\n        call: eikon-rdp.get-intraday-summaries\n        with:\n          universe: rest.universe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pricing/snapshots/{universe}\n      name: pricing-snapshots\n      description: Real-time pricing snapshots.\n      operations:\n      - method: GET\n        name: get-pricing-snapshots\n        description: Retrieve current pricing snapshots.\n        call: eikon-rdp.get-pricing-snapshots\n        with:\n          universe: rest.universe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/news/headlines\n      name: news-headlines\n      description: Financial news headlines.\n      operations:\n      - method: GET\n        name: get-news-headlines\n        description: Retrieve financial\
  \ news headlines.\n        call: eikon-rdp.get-news-headlines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/news/stories/{storyId}\n      name: news-story\n      description: Full news story content.\n      operations:\n      - method: GET\n        name: get-news-story\n        description: Retrieve a full news story.\n        call: eikon-rdp.get-news-story\n        with:\n          storyId: rest.storyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/esg/scores\n      name: esg-scores\n      description: ESG scores for instruments.\n      operations:\n      - method: GET\n        name: get-esg-scores\n        description: Retrieve ESG scores.\n        call: eikon-rdp.get-esg-scores\n        with:\n          universe: rest.universe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/esg/measures\n      name: esg-measures\n      description: Detailed ESG measures.\n\
  \      operations:\n      - method: GET\n        name: get-esg-measures\n        description: Retrieve detailed ESG measures.\n        call: eikon-rdp.get-esg-measures\n        with:\n          universe: rest.universe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/symbology/lookup\n      name: symbology\n      description: Instrument identifier concordance.\n      operations:\n      - method: POST\n        name: lookup-symbology\n        description: Map between instrument identifier types.\n        call: eikon-rdp.lookup-symbology\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search/instruments\n      name: instrument-search\n      description: Instrument and entity search.\n      operations:\n      - method: POST\n        name: search-instruments\n        description: Search for instruments and organizations.\n        call: eikon-rdp.search-instruments\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: eikon-research-mcp\n    transport: http\n    description: MCP server for AI-assisted Refinitiv Eikon financial data research.\n    tools:\n    - name: get-interday-pricing\n      description: Retrieve historical interday pricing data for a financial instrument using its RIC code.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-rdp.get-interday-summaries\n      with:\n        universe: tools.universe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-intraday-pricing\n      description: Retrieve historical intraday pricing at minute or hourly intervals.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-rdp.get-intraday-summaries\n      with:\n        universe: tools.universe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pricing-snapshot\n      description: Get current real-time\
  \ or delayed pricing snapshot for one or more instruments.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-rdp.get-pricing-snapshots\n      with:\n        universe: tools.universe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-news-headlines\n      description: Search and retrieve financial news headlines from Reuters and other sources.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: eikon-rdp.get-news-headlines\n      with:\n        query: tools.query\n        count: tools.count\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-news-story\n      description: Retrieve the full content of a financial news story by its story ID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-rdp.get-news-story\n      with:\n        storyId: tools.storyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-esg-scores\n\
  \      description: Retrieve ESG (Environmental, Social, Governance) scores for financial instruments.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-rdp.get-esg-scores\n      with:\n        universe: tools.universe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-esg-measures\n      description: Retrieve detailed ESG measures and underlying data points for instruments.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-rdp.get-esg-measures\n      with:\n        universe: tools.universe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-symbology\n      description: Map between different instrument identifier types (ISIN, CUSIP, SEDOL, RIC, PermID).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-rdp.lookup-symbology\n      with:\n        universe: tools.universe\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: search-instruments\n      description: Search across instruments, organizations, and economic indicators on the Refinitiv Data Platform.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: eikon-rdp.search-instruments\n      with:\n        query: tools.query\n        view: tools.view\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
