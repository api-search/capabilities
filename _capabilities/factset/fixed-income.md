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
- get terms and conditions.
- optimize fi portfolio
- batch fixed income analytics.
- get terms conditions
- financial data
- portfolio analytics
- get fixed income terms and conditions.
- fixed income calculations.
- financial
- market data
- bond analytics
- get fi calculations.
- research
- credit analysis
- get fi calc
- batch fi analytics
- get evaluated prices.
- get evaluated prices
- get terms
- s&p global evaluated prices.
- run fixed income calculation.
- optimize fixed income portfolio.
- investment analytics
- factset
- fixed income
- run fi calculation
- fixed income terms and conditions.
- get s&p global evaluated prices.
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
