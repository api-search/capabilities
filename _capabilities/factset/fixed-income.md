---
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
- get s&p global evaluated prices.
- get terms
- get terms conditions
- optimize fi portfolio
- batch fi analytics
- get evaluated prices.
- optimize fixed income portfolio.
- bond analytics
- financial
- run fixed income calculation.
- get fixed income terms and conditions.
- batch fixed income analytics.
- get fi calc
- credit analysis
- research
- get fi calculations.
- portfolio analytics
- s&p global evaluated prices.
- market data
- get terms and conditions.
- fixed income calculations.
- run fi calculation
- fixed income
- factset
- get evaluated prices
- financial data
- fixed income terms and conditions.
- investment analytics
slug: fixed-income
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
