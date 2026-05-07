---
categories: []
consumed_apis: []
description: Aggregated AI-ready snapshot of technical, quantitative, sentiment, risk, and performance data for a single stock or ETF symbol, optimized for consumption by AI agents and LLMs.
layout: capability
name: ValueRay Symbol Data API
operations:
- description: Retrieve AI-ready aggregated symbol data for a stock or ETF.
  method: GET
  name: getSymbolData
  path: /symbolData
personas: []
provider_name: ValueRay
provider_slug: valueray
search_terms:
- stocks
- quantitative
- valueray
- getSymbolData
- ai/llm
- etf
- retrieve ai-ready aggregated technical, quantitative, sentiment, risk, and performance data for a stock or etf symbol.
- retrieve ai-ready aggregated symbol data for a stock or etf.
- financial data
- technical analysis
slug: valueray-symbol-data-capability
source_filename: valueray-symbol-data-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ValueRay Symbol Data API\n  description: Aggregated AI-ready snapshot of technical, quantitative, sentiment,\n    risk, and performance data for a single stock or ETF symbol, optimized for\n    consumption by AI agents and LLMs.\n  tags:\n    - ValueRay\n    - AI/LLM\n    - ETF\n    - Financial Data\n    - Quantitative\n    - Stocks\n    - Technical Analysis\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n    - type: http\n      namespace: valueray\n      baseUri: https://www.valueray.com/api/v1\n      description: ValueRay Symbol Data HTTP API.\n      resources:\n        - name: symbol-data\n          path: /symbolData\n          operations:\n            - name: getSymbolData\n              method: GET\n              description: Retrieve AI-ready aggregated symbol data for a stock or ETF.\n              inputParameters:\n                - name: symbol\n                  in: query\n                  type:\
  \ string\n                  required: true\n                  description: Ticker symbol of the stock or ETF (e.g., AAPL, SPY).\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: $.\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: valueray-rest\n      description: REST adapter for the ValueRay Symbol Data API.\n      resources:\n        - path: /symbolData\n          name: getSymbolData\n          operations:\n            - method: GET\n              name: getSymbolData\n              description: Retrieve AI-ready aggregated symbol data for a stock or ETF.\n              call: valueray.getSymbolData\n              with:\n                symbol: rest.symbol\n              outputParameters:\n                - type: object\n                  mapping: $.\n    - type: mcp\n      port: 9090\n      namespace: valueray-mcp\n      transport: http\n      description: MCP\
  \ adapter for the ValueRay Symbol Data API for AI agent use.\n      tools:\n        - name: getSymbolData\n          description: Retrieve AI-ready aggregated technical, quantitative, sentiment, risk,\n            and performance data for a stock or ETF symbol.\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: valueray.getSymbolData\n          with:\n            symbol: tools.symbol\n          inputParameters:\n            - name: symbol\n              type: string\n              description: Ticker symbol of the stock or ETF (e.g., AAPL, SPY).\n              required: true\n          outputParameters:\n            - type: object\n              mapping: $.\nbinds: []\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/valueray/refs/heads/main/capabilities/valueray-symbol-data-capability.yaml
tags:
- ValueRay
- AI/LLM
- ETF
- Financial Data
- Quantitative
- Stocks
- Technical Analysis
tools:
- description: Retrieve AI-ready aggregated technical, quantitative, sentiment, risk, and performance data for a stock or ETF symbol.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getSymbolData
---
