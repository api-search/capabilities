---
categories: []
consumed_apis:
- capital-iq
- commodity-insights
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
- get commodity symbols
- get company financials
- analytics
- commodity symbol reference data
- retrieve historical commodity price data for trend analysis
- retrieve latest commodity price assessments
- get reference data for commodity symbols
- current commodity price assessments
- look up commodity symbol metadata including description, unit, and currency
- retrieve financial metrics for public or private companies from s&p capital iq
- enterprise
- market intelligence
- get commodity price history
- financial data for public and private companies
- credit ratings
- financial data
- s&p global
- historical commodity price data
- commodity insights
- lookup commodity symbol
- get commodity prices
- retrieve historical commodity price assessments
- fortune 500
- get the latest commodity price assessments from s&p global platts
- retrieve financial metrics for companies using capital iq mnemonics
slug: market-intelligence
source_filename: market-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"S&P Global Market Intelligence\"\n  description: >-\n    Unified capability combining S&P Capital IQ financial data and Commodity\n    Insights price assessments for comprehensive market intelligence workflows.\n    Used by financial analysts, portfolio managers, and commodity traders to\n    research company financials alongside market price data.\n  tags:\n    - Market Intelligence\n    - Financial Data\n    - Commodity Insights\n    - Analytics\n    - S&P Global\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      CAPITAL_IQ_API_KEY: CAPITAL_IQ_API_KEY\n      PLATTS_API_TOKEN: PLATTS_API_TOKEN\n\ncapability:\n  consumes:\n    - import: capital-iq\n      location: ./shared/capital-iq.yaml\n    - import: commodity-insights\n      location: ./shared/commodity-insights.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: market-intelligence-api\n      description:\
  \ \"Unified REST API for S&P Global market intelligence and commodity data.\"\n      resources:\n        - path: /v1/companies/financials\n          name: company-financials\n          description: \"Financial data for public and private companies\"\n          operations:\n            - method: POST\n              name: get-company-financials\n              description: \"Retrieve financial metrics for companies using Capital IQ mnemonics\"\n              call: \"capital-iq.get-financial-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/commodities/prices\n          name: commodity-prices\n          description: \"Current commodity price assessments\"\n          operations:\n            - method: GET\n              name: get-commodity-prices\n              description: \"Retrieve latest commodity price assessments\"\n              call: \"commodity-insights.get-latest-prices\"\n              with:\n       \
  \         symbol: \"rest.symbol\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/commodities/history\n          name: commodity-price-history\n          description: \"Historical commodity price data\"\n          operations:\n            - method: GET\n              name: get-commodity-price-history\n              description: \"Retrieve historical commodity price assessments\"\n              call: \"commodity-insights.get-price-history\"\n              with:\n                symbol: \"rest.symbol\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/commodities/symbols\n          name: commodity-symbols\n          description: \"Commodity symbol reference data\"\n          operations:\n            - method: GET\n              name: get-commodity-symbols\n\
  \              description: \"Get reference data for commodity symbols\"\n              call: \"commodity-insights.get-symbol-reference-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: market-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted S&P Global market intelligence research.\"\n      tools:\n        - name: get-company-financials\n          description: \"Retrieve financial metrics for public or private companies from S&P Capital IQ\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"capital-iq.get-financial-data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-commodity-prices\n          description: \"Get the latest commodity price assessments from S&P Global Platts\"\n          hints:\n            readOnly: true\n     \
  \       openWorld: true\n          call: \"commodity-insights.get-latest-prices\"\n          with:\n            symbol: \"tools.symbol\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-commodity-price-history\n          description: \"Retrieve historical commodity price data for trend analysis\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"commodity-insights.get-price-history\"\n          with:\n            symbol: \"tools.symbol\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: lookup-commodity-symbol\n          description: \"Look up commodity symbol metadata including description, unit, and currency\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"commodity-insights.get-symbol-reference-data\"\
  \n          with:\n            symbol: \"tools.symbol\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
