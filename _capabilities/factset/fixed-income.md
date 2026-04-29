---
categories: []
consumed_apis:
- factset-terms
- factset-sp-fi
- factset-fi-calc
- factset-fi-batch
- factset-axioma-fi
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
- get terms
- s&p global evaluated prices.
- get fixed income terms and conditions.
- run fixed income calculation.
- get s&p global evaluated prices.
- batch fi analytics
- get fi calc
- portfolio analytics
- batch fixed income analytics.
- get evaluated prices
- get terms and conditions.
- credit analysis
- fixed income
- run fi calculation
- optimize fi portfolio
- fixed income terms and conditions.
- fixed income calculations.
- financial data
- factset
- financial
- market data
- get terms conditions
- bond analytics
- optimize fixed income portfolio.
- get fi calculations.
- research
- get evaluated prices.
- investment analytics
slug: fixed-income
source_filename: fixed-income.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"FactSet Fixed Income\"\n  description: \"Unified workflow for fixed income analytics including terms and conditions, evaluated prices, analytics calculations, and optimization. Used by fixed income analysts.\"\n  tags:\n    - FactSet\n    - Fixed Income\n    - Bond Analytics\n    - Credit Analysis\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTSET_USERNAME: FACTSET_USERNAME\n      FACTSET_PASSWORD: FACTSET_PASSWORD\n\ncapability:\n  consumes:\n    - import: factset-terms\n      location: ./shared/terms-and-conditions.yaml\n    - import: factset-sp-fi\n      location: ./shared/s-p-global-fixed-income-evaluated-prices-and-analytics.yaml\n    - import: factset-fi-calc\n      location: ./shared/fixed-income-calculation.yaml\n    - import: factset-fi-batch\n      location: ./shared/fixed-income-analytics-batcher.yaml\n    - import: factset-axioma-fi\n      location: ./shared/axioma-fixed-income-optimizer.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8084\n      namespace: fixed-income-api\n      description: \"Unified REST API for fixed income analytics.\"\n      resources:\n        - path: /v1/terms-conditions\n          name: terms-conditions\n          description: \"Fixed income terms and conditions.\"\n          operations:\n            - method: GET\n              name: get-terms\n              description: \"Get terms and conditions.\"\n              call: \"factset-terms.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/evaluated-prices\n          name: evaluated-prices\n          description: \"S&P Global evaluated prices.\"\n          operations:\n            - method: GET\n              name: get-evaluated-prices\n              description: \"Get evaluated prices.\"\n              call: \"factset-sp-fi.list\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/fi-calculations\n          name: fi-calculations\n          description: \"Fixed income calculations.\"\n          operations:\n            - method: GET\n              name: get-fi-calc\n              description: \"Get FI calculations.\"\n              call: \"factset-fi-calc.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9084\n      namespace: fixed-income-mcp\n      transport: http\n      description: \"MCP server for AI-assisted fixed income analysis.\"\n      tools:\n        - name: get-terms-conditions\n          description: \"Get fixed income terms and conditions.\"\n          hints:\n            readOnly: true\n          call: \"factset-terms.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-evaluated-prices\n          description: \"Get S&P Global evaluated prices.\"\n          hints:\n   \
  \         readOnly: true\n          call: \"factset-sp-fi.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-fi-calculation\n          description: \"Run fixed income calculation.\"\n          hints:\n            readOnly: true\n          call: \"factset-fi-calc.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-fi-analytics\n          description: \"Batch fixed income analytics.\"\n          hints:\n            readOnly: true\n          call: \"factset-fi-batch.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: optimize-fi-portfolio\n          description: \"Optimize fixed income portfolio.\"\n          hints:\n            readOnly: true\n          call: \"factset-axioma-fi.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
