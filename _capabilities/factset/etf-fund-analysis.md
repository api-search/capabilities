---
categories: []
consumed_apis: []
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
- get etfs
- funds
- research
- investment analytics
- market data
- get mutual fund data.
- fund data.
- get benchmark data.
- etf data.
- portfolio analytics
- factset
- get etf data
- financial data
- get etf profiles
- get fund data
- get funds
- get consensus estimates.
- get etf reference data.
- get etf data.
- financial
- get estimates
- benchmark data.
- benchmarks
- etf
- get benchmarks
- get etf profiles and prices.
- get fund data.
slug: etf-fund-analysis
source_filename: etf-fund-analysis.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FactSet ETF and Fund Analysis\n  description: Unified workflow for ETF and mutual fund analysis including profiles, pricing, allocations, performance, and\n    benchmarks. Used by fund analysts.\n  tags:\n  - FactSet\n  - ETF\n  - Funds\n  - Benchmarks\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACTSET_USERNAME: FACTSET_USERNAME\n    FACTSET_PASSWORD: FACTSET_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n  \
  \    operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username:\
  \ '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8088\n    namespace: etf-fund-api\n    description: Unified REST API for ETF and fund analysis.\n    resources:\n    - path: /v1/etfs\n      name: etfs\n      description: ETF data.\n      operations:\n      - method: GET\n        name: get-etfs\n        description: Get ETF data.\n        call: factset-etf.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/funds\n      name: funds\n      description: Fund data.\n      operations:\n      - method: GET\n        name: get-funds\n        description: Get fund data.\n\
  \        call: factset-funds.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/benchmarks\n      name: benchmarks\n      description: Benchmark data.\n      operations:\n      - method: GET\n        name: get-benchmarks\n        description: Get benchmark data.\n        call: factset-benchmarks.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9088\n    namespace: etf-fund-mcp\n    transport: http\n    description: MCP server for AI-assisted ETF and fund analysis.\n    tools:\n    - name: get-etf-data\n      description: Get ETF reference data.\n      hints:\n        readOnly: true\n      call: factset-etf.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-etf-profiles\n      description: Get ETF profiles and prices.\n      hints:\n        readOnly: true\n      call: factset-etf-profile.list\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-fund-data\n      description: Get mutual fund data.\n      hints:\n        readOnly: true\n      call: factset-funds.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-benchmarks\n      description: Get benchmark data.\n      hints:\n        readOnly: true\n      call: factset-benchmarks.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-estimates\n      description: Get consensus estimates.\n      hints:\n        readOnly: true\n      call: factset-estimates.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/etf-fund-analysis.yaml
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
