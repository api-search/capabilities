---
categories: []
consumed_apis: []
description: Commodity market data workflow combining real-time and historical price assessments, symbol discovery, and incremental data sync from S&P Global Commodity Insights (Platts). Used by energy traders, analysts, risk managers, and quant teams.
layout: capability
name: S&P Global Commodity Market Data
operations:
- description: Get current price assessments for specified commodity symbols
  method: GET
  name: get-current-prices
  path: /v1/prices/current
- description: Get historical price assessments over a date range
  method: GET
  name: get-price-history
  path: /v1/prices/history
- description: List available commodity symbols with metadata
  method: GET
  name: list-symbols
  path: /v1/symbols
- description: Get symbols modified since a date for incremental sync
  method: GET
  name: get-modified-symbols
  path: /v1/symbols/modified
personas: []
provider_name: S&P Global
provider_slug: s-and-p-global
search_terms:
- analytics
- get historical price assessments over a date range
- list symbols
- energy markets
- get current price assessments for specified commodity symbols
- get the latest price assessments for platts commodity symbols (e.g., pcaas00 for dated brent crude oil). returns current value, unit of measure, currency, and assessment date.
- get symbols modified since a date for incremental sync
- get modified commodity symbols
- get current prices
- get current commodity prices
- historical commodity price assessments
- commodity insights
- symbols modified since a date
- get modified symbols
- credit ratings
- financial data
- get price history
- market intelligence
- commodity symbol reference data
- trading
- get historical commodity price assessments for a date range. use for time series analysis, backtesting, and trend analysis in energy and commodity markets.
- get list of commodity symbols with updated price assessments since a given date. use for incremental data sync to keep commodity price databases current.
- s&p global
- list available commodity symbols with metadata
- market data
- list available platts commodity symbols with descriptions, units, and assessment frequency. filter by commodity name (crude oil, natural gas, lng, etc.).
- capital markets
- get historical commodity prices
- current commodity price assessments
- fortune 500
- list commodity symbols
slug: commodity-market-data
source_filename: commodity-market-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: S&P Global Commodity Market Data\n  description: Commodity market data workflow combining real-time and historical price assessments, symbol discovery, and\n    incremental data sync from S&P Global Commodity Insights (Platts). Used by energy traders, analysts, risk managers, and\n    quant teams.\n  tags:\n  - S&P Global\n  - Commodity Insights\n  - Energy Markets\n  - Market Data\n  - Trading\n  - Analytics\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPG_CI_ACCESS_TOKEN: SPG_CI_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: spg-commodity-insights\n    baseUri: https://api.platts.com\n    description: S&P Global Commodity Insights REST API\n    authentication:\n      type: bearer\n      token: '{{SPG_CI_ACCESS_TOKEN}}'\n    resources:\n    - name: authentication\n      path: /auth/api\n      description: Token authentication\n      operations:\n      - name: authenticate\n\
  \        method: POST\n        description: Exchange credentials for Bearer access token\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n    - name: current-market-data\n      path: /market-data/v1/value/current\n      description: Current commodity price assessments\n      operations:\n      - name: get-current-market-data\n        method: GET\n        description: Get most recent assessment values for specified commodity symbols\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n          description: Comma-separated Platts symbol codes (e.g., PCAAS00,AAPTA00)\n        - name: format\n          in: query\n          type: string\n          required: false\n          description:\
  \ 'Response format: json or xml'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historical-market-data\n      path: /market-data/v1/value/history\n      description: Historical commodity price assessments\n      operations:\n      - name: get-historical-market-data\n        method: GET\n        description: Get historical assessment values for commodity symbols over a date range\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n          description: Comma-separated commodity symbol codes\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start date (YYYY-MM-DD)\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: End date (YYYY-MM-DD)\n        - name: pageSize\n          in: query\n    \
  \      type: integer\n          required: false\n          description: Records per page (max 1000)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: symbols\n      path: /market-data/v1/symbols\n      description: Commodity symbol reference data\n      operations:\n      - name: list-symbols\n        method: GET\n        description: List available commodity symbols with descriptions and units\n        inputParameters:\n        - name: commodityName\n          in: query\n          type: string\n          required: false\n          description: Filter by commodity name\n        - name: assessmentFrequency\n          in: query\n          type: string\n          required: false\n          description: 'Filter by frequency: Daily, Weekly, Monthly'\n        - name: pageSize\n\
  \          in: query\n          type: integer\n          required: false\n          description: Records per page\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: modified-symbols\n      path: /market-data/v1/modified-date\n      description: Symbols modified since a given date\n      operations:\n      - name: get-modified-symbols\n        method: GET\n        description: Get symbols whose values have been modified since a date\n        inputParameters:\n        - name: modifiedDate\n          in: query\n          type: string\n          required: true\n          description: Return symbols modified after this date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: commodity-market-data-api\n    description: Unified REST API for S&P Global commodity market data access.\n    resources:\n    - path: /v1/prices/current\n      name: current-prices\n      description: Current commodity price assessments\n      operations:\n      - method: GET\n        name: get-current-prices\n        description: Get current price assessments for specified commodity symbols\n        call: spg-commodity-insights.get-current-market-data\n        with:\n          symbol: rest.symbol\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/prices/history\n      name: price-history\n      description: Historical commodity price assessments\n      operations:\n      - method: GET\n        name: get-price-history\n        description: Get historical price assessments over a date range\n        call: spg-commodity-insights.get-historical-market-data\n        with:\n\
  \          symbol: rest.symbol\n          startDate: rest.startDate\n          endDate: rest.endDate\n          pageSize: rest.pageSize\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/symbols\n      name: symbols\n      description: Commodity symbol reference data\n      operations:\n      - method: GET\n        name: list-symbols\n        description: List available commodity symbols with metadata\n        call: spg-commodity-insights.list-symbols\n        with:\n          commodityName: rest.commodityName\n          assessmentFrequency: rest.assessmentFrequency\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/symbols/modified\n      name: modified-symbols\n      description: Symbols modified since a date\n      operations:\n      - method: GET\n        name: get-modified-symbols\n        description: Get symbols modified since a date for incremental sync\n        call: spg-commodity-insights.get-modified-symbols\n\
  \        with:\n          modifiedDate: rest.modifiedDate\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: commodity-market-data-mcp\n    transport: http\n    description: MCP server for AI-assisted commodity market data analysis and energy market research.\n    tools:\n    - name: get-current-commodity-prices\n      description: Get the latest price assessments for Platts commodity symbols (e.g., PCAAS00 for Dated Brent crude oil).\n        Returns current value, unit of measure, currency, and assessment date.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spg-commodity-insights.get-current-market-data\n      with:\n        symbol: tools.symbol\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-historical-commodity-prices\n      description: Get historical commodity price assessments for a date range. Use for time series analysis, backtesting,\n     \
  \   and trend analysis in energy and commodity markets.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spg-commodity-insights.get-historical-market-data\n      with:\n        symbol: tools.symbol\n        startDate: tools.startDate\n        endDate: tools.endDate\n        pageSize: tools.pageSize\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-commodity-symbols\n      description: List available Platts commodity symbols with descriptions, units, and assessment frequency. Filter by commodity\n        name (Crude Oil, Natural Gas, LNG, etc.).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spg-commodity-insights.list-symbols\n      with:\n        commodityName: tools.commodityName\n        assessmentFrequency: tools.assessmentFrequency\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-modified-commodity-symbols\n      description: Get\
  \ list of commodity symbols with updated price assessments since a given date. Use for incremental data\n        sync to keep commodity price databases current.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spg-commodity-insights.get-modified-symbols\n      with:\n        modifiedDate: tools.modifiedDate\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/s-and-p-global/refs/heads/main/capabilities/commodity-market-data.yaml
tags:
- S&P Global
- Commodity Insights
- Energy Markets
- Market Data
- Trading
- Analytics
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
- description: Get list of commodity symbols with updated price assessments since a given date. Use for incremental data sync to keep commodity price databases current.
  hints:
    openWorld: false
    readOnly: true
  name: get-modified-commodity-symbols
---
