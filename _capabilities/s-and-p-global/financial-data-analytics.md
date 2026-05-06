---
categories: []
consumed_apis: []
description: Unified financial data analytics workflow combining S&P Global Commodity Insights market data with Kensho entity resolution. Used by financial analysts, quant teams, energy traders, and data scientists to integrate commodity pricing with entity identification across S&P Global data assets.
layout: capability
name: S&P Global Financial Data Analytics
operations:
- description: Get current price assessments for specified commodity symbols
  method: GET
  name: get-current-prices
  path: /v1/prices/current
- description: Get historical price assessments over a date range
  method: GET
  name: get-price-history
  path: /v1/prices/history
- description: List available commodity symbols
  method: GET
  name: list-symbols
  path: /v1/symbols
- description: Resolve entity mentions to canonical KEIDs
  method: POST
  name: link-entity
  path: /v1/entities/link
- description: Get entity record by KEID with cross-references
  method: GET
  name: get-entity
  path: /v1/entities/{keid}
- description: Search for financial entities
  method: GET
  name: search-entities
  path: /v1/entities/search
personas: []
provider_name: S&P Global
provider_slug: s-and-p-global
search_terms:
- entity resolution
- get historical commodity price assessments for a date range. use for time series analysis, backtesting, and trend analysis in energy and commodity markets.
- resolve a financial entity mention (company name, ticker, cusip, isin) to its canonical kensho entity identifier (keid) with confidence scores and cross-references.
- credit ratings
- market data
- analytics
- get historical price assessments over a date range
- search entities
- resolve entity mentions to canonical keids
- current commodity price assessments
- search financial entities
- get current commodity prices
- canonical entity record
- entity resolution and linking
- get entity record by keid with cross-references
- entity search by name or identifier
- list symbols
- commodity symbol reference data
- trading
- get modified commodity symbols
- search for financial entities
- financial data
- get current prices
- s&p global
- energy markets
- get entity
- get current price assessments for specified commodity symbols
- get historical commodity prices
- historical commodity price assessments
- fortune 500
- list available platts commodity symbols with descriptions, units, and assessment frequency. filter by commodity name (crude oil, natural gas, lng, etc.).
- link financial entity
- get the full canonical entity record for a keid including aliases, cross-references (ticker, cusip, isin, lei, s&p global company id).
- commodity insights
- market intelligence
- list commodity symbols
- capital markets
- get the latest price assessments for platts commodity symbols (e.g., pcaas00 for dated brent crude oil). returns current value, unit of measure, currency, and assessment date.
- link entity
- get price history
- get entity by keid
- get list of commodity symbols with updated price assessments since a given date. use for incremental data sync.
- list available commodity symbols
- search for financial entities (companies, instruments, funds, indices) by name or identifier. returns ranked candidates with confidence scores.
slug: financial-data-analytics
source_filename: financial-data-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: S&P Global Financial Data Analytics\n  description: Unified financial data analytics workflow combining S&P Global Commodity Insights market data with Kensho entity\n    resolution. Used by financial analysts, quant teams, energy traders, and data scientists to integrate commodity pricing\n    with entity identification across S&P Global data assets.\n  tags:\n  - S&P Global\n  - Financial Data\n  - Commodity Insights\n  - Entity Resolution\n  - Market Data\n  - Analytics\n  - Trading\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPG_CI_ACCESS_TOKEN: SPG_CI_ACCESS_TOKEN\n    KENSHO_LINK_TOKEN: KENSHO_LINK_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: spg-commodity-insights\n    baseUri: https://api.platts.com\n    description: S&P Global Commodity Insights REST API\n    authentication:\n      type: bearer\n      token: '{{SPG_CI_ACCESS_TOKEN}}'\n    resources:\n    - name:\
  \ authentication\n      path: /auth/api\n      description: Token authentication\n      operations:\n      - name: authenticate\n        method: POST\n        description: Exchange credentials for Bearer access token\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n    - name: current-market-data\n      path: /market-data/v1/value/current\n      description: Current commodity price assessments\n      operations:\n      - name: get-current-market-data\n        method: GET\n        description: Get most recent assessment values for specified commodity symbols\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n          description: Comma-separated Platts symbol codes (e.g.,\
  \ PCAAS00,AAPTA00)\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or xml'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historical-market-data\n      path: /market-data/v1/value/history\n      description: Historical commodity price assessments\n      operations:\n      - name: get-historical-market-data\n        method: GET\n        description: Get historical assessment values for commodity symbols over a date range\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n          description: Comma-separated commodity symbol codes\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start date (YYYY-MM-DD)\n        - name: endDate\n          in: query\n          type:\
  \ string\n          required: true\n          description: End date (YYYY-MM-DD)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Records per page (max 1000)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: symbols\n      path: /market-data/v1/symbols\n      description: Commodity symbol reference data\n      operations:\n      - name: list-symbols\n        method: GET\n        description: List available commodity symbols with descriptions and units\n        inputParameters:\n        - name: commodityName\n          in: query\n          type: string\n          required: false\n          description: Filter by commodity name\n        - name: assessmentFrequency\n          in: query\n          type:\
  \ string\n          required: false\n          description: 'Filter by frequency: Daily, Weekly, Monthly'\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: modified-symbols\n      path: /market-data/v1/modified-date\n      description: Symbols modified since a given date\n      operations:\n      - name: get-modified-symbols\n        method: GET\n        description: Get symbols whose values have been modified since a date\n        inputParameters:\n        - name: modifiedDate\n          in: query\n          type: string\n          required: true\n          description: Return symbols modified after this date (YYYY-MM-DD)\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: kensho-link\n    baseUri: https://api.link.kensho.com\n    description: Kensho Link entity resolution REST API\n    authentication:\n      type: bearer\n      token: '{{KENSHO_LINK_TOKEN}}'\n    resources:\n    - name: link\n      path: /link\n      description: Entity mention resolution to canonical KEIDs\n      operations:\n      - name: link-entity\n        method: POST\n        description: Resolve entity mentions to canonical Kensho Entity Identifiers\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            mentions: '{{tools.mentions}}'\n            context: '{{tools.context}}'\n    - name: entity\n      path: /entity\n      description: Entity record retrieval by KEID\n\
  \      operations:\n      - name: get-entity\n        method: GET\n        description: Get full entity record including aliases and cross-references by KEID\n        inputParameters:\n        - name: keid\n          in: path\n          type: string\n          required: true\n          description: Kensho Entity Identifier (KEID)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Entity search by name or identifier\n      operations:\n      - name: search-entities\n        method: GET\n        description: Search for entities by name, ticker, or other attributes\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query (entity name, ticker, or identifier)\n        - name: entityType\n          in: query\n          type: string\n          required: false\n  \
  \        description: 'Filter by entity type: company, person, instrument, fund, index'\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return (max 50)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: financial-data-analytics-api\n    description: Unified REST API for S&P Global financial data analytics combining commodity market data and entity resolution.\n    resources:\n    - path: /v1/prices/current\n      name: current-prices\n      description: Current commodity price assessments\n      operations:\n      - method: GET\n        name: get-current-prices\n        description: Get current price assessments for specified commodity symbols\n        call: spg-commodity-insights.get-current-market-data\n        with:\n          symbol: rest.symbol\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/prices/history\n      name: price-history\n      description: Historical commodity price assessments\n      operations:\n      - method: GET\n        name: get-price-history\n        description: Get historical price assessments over a date range\n        call: spg-commodity-insights.get-historical-market-data\n        with:\n          symbol: rest.symbol\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/symbols\n      name: symbols\n      description: Commodity symbol reference data\n      operations:\n      - method: GET\n        name: list-symbols\n        description: List available commodity symbols\n        call: spg-commodity-insights.list-symbols\n        with:\n          commodityName: rest.commodityName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/link\n\
  \      name: entity-link\n      description: Entity resolution and linking\n      operations:\n      - method: POST\n        name: link-entity\n        description: Resolve entity mentions to canonical KEIDs\n        call: kensho-link.link-entity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/{keid}\n      name: entity\n      description: Canonical entity record\n      operations:\n      - method: GET\n        name: get-entity\n        description: Get entity record by KEID with cross-references\n        call: kensho-link.get-entity\n        with:\n          keid: rest.keid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/search\n      name: entity-search\n      description: Entity search by name or identifier\n      operations:\n      - method: GET\n        name: search-entities\n        description: Search for financial entities\n        call: kensho-link.search-entities\n        with:\n\
  \          q: rest.q\n          entityType: rest.entityType\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: financial-data-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted financial data analysis combining commodity pricing and entity intelligence.\n    tools:\n    - name: get-current-commodity-prices\n      description: Get the latest price assessments for Platts commodity symbols (e.g., PCAAS00 for Dated Brent crude oil).\n        Returns current value, unit of measure, currency, and assessment date.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spg-commodity-insights.get-current-market-data\n      with:\n        symbol: tools.symbol\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-historical-commodity-prices\n      description: Get historical commodity price assessments for a date range. Use for time series analysis,\
  \ backtesting,\n        and trend analysis in energy and commodity markets.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spg-commodity-insights.get-historical-market-data\n      with:\n        symbol: tools.symbol\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-commodity-symbols\n      description: List available Platts commodity symbols with descriptions, units, and assessment frequency. Filter by commodity\n        name (Crude Oil, Natural Gas, LNG, etc.).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spg-commodity-insights.list-symbols\n      with:\n        commodityName: tools.commodityName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-modified-commodity-symbols\n      description: Get list of commodity symbols with updated price assessments since a given date. Use for incremental\
  \ data\n        sync.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spg-commodity-insights.get-modified-symbols\n      with:\n        modifiedDate: tools.modifiedDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: link-financial-entity\n      description: Resolve a financial entity mention (company name, ticker, CUSIP, ISIN) to its canonical Kensho Entity Identifier\n        (KEID) with confidence scores and cross-references.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: kensho-link.link-entity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-entity-by-keid\n      description: Get the full canonical entity record for a KEID including aliases, cross-references (ticker, CUSIP, ISIN,\n        LEI, S&P Global Company ID).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: kensho-link.get-entity\n      with:\n        keid: tools.keid\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-financial-entities\n      description: Search for financial entities (companies, instruments, funds, indices) by name or identifier. Returns ranked\n        candidates with confidence scores.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: kensho-link.search-entities\n      with:\n        q: tools.q\n        entityType: tools.entityType\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/s-and-p-global/refs/heads/main/capabilities/financial-data-analytics.yaml
tags:
- S&P Global
- Financial Data
- Commodity Insights
- Entity Resolution
- Market Data
- Analytics
- Trading
tools:
- description: Get the latest price assessments for Platts commodity symbols (e.g., PCAAS00 for Dated Brent crude oil). Returns current value, unit of measure, currency, and assessment date.
  hints:
    openWorld: false
    readOnly: true
  name: get-current-commodity-prices
- description: Get historical commodity price assessments for a date range. Use for time series analysis, backtesting, and trend analysis in energy and commodity markets.
  hints:
    openWorld: false
    readOnly: true
  name: get-historical-commodity-prices
- description: List available Platts commodity symbols with descriptions, units, and assessment frequency. Filter by commodity name (Crude Oil, Natural Gas, LNG, etc.).
  hints:
    openWorld: false
    readOnly: true
  name: list-commodity-symbols
- description: Get list of commodity symbols with updated price assessments since a given date. Use for incremental data sync.
  hints:
    openWorld: false
    readOnly: true
  name: get-modified-commodity-symbols
- description: Resolve a financial entity mention (company name, ticker, CUSIP, ISIN) to its canonical Kensho Entity Identifier (KEID) with confidence scores and cross-references.
  hints:
    openWorld: false
    readOnly: true
  name: link-financial-entity
- description: Get the full canonical entity record for a KEID including aliases, cross-references (ticker, CUSIP, ISIN, LEI, S&P Global Company ID).
  hints:
    openWorld: false
    readOnly: true
  name: get-entity-by-keid
- description: Search for financial entities (companies, instruments, funds, indices) by name or identifier. Returns ranked candidates with confidence scores.
  hints:
    openWorld: false
    readOnly: true
  name: search-financial-entities
---
