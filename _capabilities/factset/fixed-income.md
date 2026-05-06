---
categories: []
consumed_apis: []
description: Unified workflow for fixed income analytics including terms and conditions, evaluated prices, analytics calculations, and optimization. Used by fixed income analysts.
layout: capability
name: FactSet Fixed Income
operations:
- description: Get terms and conditions.
  method: GET
  name: get-terms
  path: /v1/terms-conditions
- description: Get evaluated prices.
  method: GET
  name: get-evaluated-prices
  path: /v1/evaluated-prices
- description: Get FI calculations.
  method: GET
  name: get-fi-calc
  path: /v1/fi-calculations
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- run fi calculation
- get fixed income terms and conditions.
- get evaluated prices
- fixed income terms and conditions.
- research
- fixed income calculations.
- batch fi analytics
- get terms
- investment analytics
- get fi calculations.
- optimize fixed income portfolio.
- get evaluated prices.
- market data
- run fixed income calculation.
- get fi calc
- batch fixed income analytics.
- get terms conditions
- portfolio analytics
- factset
- fixed income
- get terms and conditions.
- s&p global evaluated prices.
- credit analysis
- financial data
- get s&p global evaluated prices.
- optimize fi portfolio
- financial
- bond analytics
slug: fixed-income
source_filename: fixed-income.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FactSet Fixed Income\n  description: Unified workflow for fixed income analytics including terms and conditions, evaluated prices, analytics calculations,\n    and optimization. Used by fixed income analysts.\n  tags:\n  - FactSet\n  - Fixed Income\n  - Bond Analytics\n  - Credit Analysis\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACTSET_USERNAME: FACTSET_USERNAME\n    FACTSET_PASSWORD: FACTSET_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description:\
  \ Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n\
  \      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: fixed-income-api\n    description: Unified REST API for fixed income analytics.\n    resources:\n    - path: /v1/terms-conditions\n      name: terms-conditions\n      description: Fixed income terms and conditions.\n      operations:\n      - method: GET\n        name: get-terms\n        description: Get terms and conditions.\n        call: factset-terms.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/evaluated-prices\n      name: evaluated-prices\n   \
  \   description: S&P Global evaluated prices.\n      operations:\n      - method: GET\n        name: get-evaluated-prices\n        description: Get evaluated prices.\n        call: factset-sp-fi.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fi-calculations\n      name: fi-calculations\n      description: Fixed income calculations.\n      operations:\n      - method: GET\n        name: get-fi-calc\n        description: Get FI calculations.\n        call: factset-fi-calc.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9084\n    namespace: fixed-income-mcp\n    transport: http\n    description: MCP server for AI-assisted fixed income analysis.\n    tools:\n    - name: get-terms-conditions\n      description: Get fixed income terms and conditions.\n      hints:\n        readOnly: true\n      call: factset-terms.list\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: get-evaluated-prices\n      description: Get S&P Global evaluated prices.\n      hints:\n        readOnly: true\n      call: factset-sp-fi.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-fi-calculation\n      description: Run fixed income calculation.\n      hints:\n        readOnly: true\n      call: factset-fi-calc.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-fi-analytics\n      description: Batch fixed income analytics.\n      hints:\n        readOnly: true\n      call: factset-fi-batch.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: optimize-fi-portfolio\n      description: Optimize fixed income portfolio.\n      hints:\n        readOnly: true\n      call: factset-axioma-fi.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/fixed-income.yaml
tags:
- FactSet
- Fixed Income
- Bond Analytics
- Credit Analysis
tools:
- description: Get fixed income terms and conditions.
  hints:
    readOnly: true
  name: get-terms-conditions
- description: Get S&P Global evaluated prices.
  hints:
    readOnly: true
  name: get-evaluated-prices
- description: Run fixed income calculation.
  hints:
    readOnly: true
  name: run-fi-calculation
- description: Batch fixed income analytics.
  hints:
    readOnly: true
  name: batch-fi-analytics
- description: Optimize fixed income portfolio.
  hints:
    readOnly: true
  name: optimize-fi-portfolio
---
