---
categories: []
consumed_apis: []
description: Unified capability combining S&P Capital IQ financial data and Commodity Insights price assessments for comprehensive market intelligence workflows. Used by financial analysts, portfolio managers, and commodity traders to research company financials alongside market price data.
layout: capability
name: S&P Global Market Intelligence
operations:
- description: Retrieve financial metrics for companies using Capital IQ mnemonics
  method: POST
  name: get-company-financials
  path: /v1/companies/financials
- description: Retrieve latest commodity price assessments
  method: GET
  name: get-commodity-prices
  path: /v1/commodities/prices
- description: Retrieve historical commodity price assessments
  method: GET
  name: get-commodity-price-history
  path: /v1/commodities/history
- description: Get reference data for commodity symbols
  method: GET
  name: get-commodity-symbols
  path: /v1/commodities/symbols
personas: []
provider_name: S&P Global
provider_slug: sandp-global
search_terms:
- credit ratings
- look up commodity symbol metadata including description, unit, and currency
- retrieve latest commodity price assessments
- analytics
- current commodity price assessments
- get commodity symbols
- financial data for public and private companies
- retrieve financial metrics for companies using capital iq mnemonics
- get company financials
- enterprise
- commodity symbol reference data
- retrieve financial metrics for public or private companies from s&p capital iq
- get commodity prices
- financial data
- fortune 500
- get reference data for commodity symbols
- retrieve historical commodity price data for trend analysis
- get commodity price history
- retrieve historical commodity price assessments
- lookup commodity symbol
- commodity insights
- market intelligence
- s&p global
- historical commodity price data
- get the latest commodity price assessments from s&p global platts
slug: market-intelligence
source_filename: market-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: S&P Global Market Intelligence\n  description: Unified capability combining S&P Capital IQ financial data and Commodity Insights price assessments for comprehensive\n    market intelligence workflows. Used by financial analysts, portfolio managers, and commodity traders to research company\n    financials alongside market price data.\n  tags:\n  - Market Intelligence\n  - Financial Data\n  - Commodity Insights\n  - Analytics\n  - S&P Global\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CAPITAL_IQ_API_KEY: CAPITAL_IQ_API_KEY\n    PLATTS_API_TOKEN: PLATTS_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: capital-iq\n    baseUri: https://api-ciq.marketintelligence.spglobal.com/gdsapi/rest\n    description: S&P Capital IQ financial data API with comprehensive global company data\n    authentication:\n      type: bearer\n      token: '{{CAPITAL_IQ_API_KEY}}'\n    resources:\n  \
  \  - name: authentication\n      path: /authenticate/api/v1\n      description: Token generation and refresh\n      operations:\n      - name: generate-auth-token\n        method: POST\n        description: Generate Bearer access token using SSO credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: financial-data\n      path: /v3\n      description: Financial and market intelligence data retrieval\n      operations:\n      - name: get-financial-data\n        method: POST\n        description: Retrieve financial data for company using function, identifier, and mnemonic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: commodity-insights\n    baseUri: https://api.platts.com\n    description: S&P Global Commodity Insights (Platts) price assessment and market data API\n    authentication:\n\
  \      type: bearer\n      token: '{{PLATTS_API_TOKEN}}'\n    resources:\n    - name: prices\n      path: /v1/prices\n      description: Commodity price assessments and historical data\n      operations:\n      - name: get-latest-prices\n        method: GET\n        description: Get most recent price assessments for commodity symbols\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n          description: Comma-separated Platts symbol codes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-price-history\n        method: GET\n        description: Get historical price assessments within a date range\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n          required: true\n          description: Comma-separated Platts symbol codes\n        - name: startDate\n          in: query\n\
  \          type: string\n          required: true\n          description: Start date YYYY-MM-DD\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: End date YYYY-MM-DD\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Records per page (default 1000)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reference\n      path: /v1/reference\n      description: Commodity reference data and symbol metadata\n      operations:\n      - name: get-symbol-reference-data\n        method: GET\n        description: Get reference data for commodity symbols\n        inputParameters:\n        - name: symbol\n          in: query\n          type: string\n\
  \          required: false\n          description: Filter by symbol codes\n        - name: commodity\n          in: query\n          type: string\n          required: false\n          description: Filter by commodity type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: market-data-content-sets\n      path: /v1/mdcs\n      description: Market data content set management\n      operations:\n      - name: get-price-groups\n        method: GET\n        description: Get available price groups and content sets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: market-intelligence-api\n    description: Unified REST API for S&P Global market intelligence and commodity data.\n    resources:\n    - path: /v1/companies/financials\n      name: company-financials\n      description:\
  \ Financial data for public and private companies\n      operations:\n      - method: POST\n        name: get-company-financials\n        description: Retrieve financial metrics for companies using Capital IQ mnemonics\n        call: capital-iq.get-financial-data\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commodities/prices\n      name: commodity-prices\n      description: Current commodity price assessments\n      operations:\n      - method: GET\n        name: get-commodity-prices\n        description: Retrieve latest commodity price assessments\n        call: commodity-insights.get-latest-prices\n        with:\n          symbol: rest.symbol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commodities/history\n      name: commodity-price-history\n      description: Historical commodity price data\n      operations:\n      - method: GET\n        name: get-commodity-price-history\n        description:\
  \ Retrieve historical commodity price assessments\n        call: commodity-insights.get-price-history\n        with:\n          symbol: rest.symbol\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commodities/symbols\n      name: commodity-symbols\n      description: Commodity symbol reference data\n      operations:\n      - method: GET\n        name: get-commodity-symbols\n        description: Get reference data for commodity symbols\n        call: commodity-insights.get-symbol-reference-data\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: market-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted S&P Global market intelligence research.\n    tools:\n    - name: get-company-financials\n      description: Retrieve financial metrics for public or private companies from S&P\
  \ Capital IQ\n      hints:\n        readOnly: true\n        openWorld: false\n      call: capital-iq.get-financial-data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commodity-prices\n      description: Get the latest commodity price assessments from S&P Global Platts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: commodity-insights.get-latest-prices\n      with:\n        symbol: tools.symbol\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commodity-price-history\n      description: Retrieve historical commodity price data for trend analysis\n      hints:\n        readOnly: true\n        openWorld: false\n      call: commodity-insights.get-price-history\n      with:\n        symbol: tools.symbol\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-commodity-symbol\n      description:\
  \ Look up commodity symbol metadata including description, unit, and currency\n      hints:\n        readOnly: true\n        openWorld: false\n      call: commodity-insights.get-symbol-reference-data\n      with:\n        symbol: tools.symbol\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sandp-global/refs/heads/main/capabilities/market-intelligence.yaml
tags:
- Market Intelligence
- Financial Data
- Commodity Insights
- Analytics
- S&P Global
tools:
- description: Retrieve financial metrics for public or private companies from S&P Capital IQ
  hints:
    openWorld: false
    readOnly: true
  name: get-company-financials
- description: Get the latest commodity price assessments from S&P Global Platts
  hints:
    openWorld: true
    readOnly: true
  name: get-commodity-prices
- description: Retrieve historical commodity price data for trend analysis
  hints:
    openWorld: false
    readOnly: true
  name: get-commodity-price-history
- description: Look up commodity symbol metadata including description, unit, and currency
  hints:
    openWorld: false
    readOnly: true
  name: lookup-commodity-symbol
---
