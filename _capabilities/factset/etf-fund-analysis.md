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
- portfolio analytics
- benchmarks
- benchmark data.
- get etf reference data.
- get etf data
- get fund data
- get etf data.
- get etfs
- market data
- get mutual fund data.
- research
- get benchmark data.
- get consensus estimates.
- etf data.
- funds
- get benchmarks
- get fund data.
- get etf profiles and prices.
- get funds
- get estimates
- investment analytics
- financial data
- get etf profiles
- etf
- financial
- factset
- fund data.
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
