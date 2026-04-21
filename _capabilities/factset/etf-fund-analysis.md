---
consumed_apis:
- factset-etf
- factset-etf-profile
- factset-funds
- factset-benchmarks
- factset-estimates
description: Unified workflow for ETF and mutual fund analysis including profiles, pricing, allocations, performance, and benchmarks. Used by fund analysts.
layout: capability
name: FactSet ETF and Fund Analysis
operations:
- description: Get ETF data.
  method: GET
  name: get-etfs
  path: /v1/etfs
- description: Get fund data.
  method: GET
  name: get-funds
  path: /v1/funds
- description: Get benchmark data.
  method: GET
  name: get-benchmarks
  path: /v1/benchmarks
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- benchmark data.
- benchmarks
- fund data.
- get etf profiles
- get funds
- get benchmark data.
- get etfs
- financial
- get etf data
- research
- portfolio analytics
- get etf profiles and prices.
- market data
- get mutual fund data.
- get fund data.
- get benchmarks
- get estimates
- get consensus estimates.
- etf data.
- get fund data
- etf
- factset
- funds
- get etf data.
- financial data
- investment analytics
- get etf reference data.
slug: etf-fund-analysis
tags:
- FactSet
- ETF
- Funds
- Benchmarks
tools:
- description: Get ETF reference data.
  hints:
    readOnly: true
  name: get-etf-data
- description: Get ETF profiles and prices.
  hints:
    readOnly: true
  name: get-etf-profiles
- description: Get mutual fund data.
  hints:
    readOnly: true
  name: get-fund-data
- description: Get benchmark data.
  hints:
    readOnly: true
  name: get-benchmarks
- description: Get consensus estimates.
  hints:
    readOnly: true
  name: get-estimates
---
