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
- investment analytics
- get evaluated prices
- credit analysis
- optimize fixed income portfolio.
- fixed income
- research
- batch fi analytics
- get fi calculations.
- factset
- market data
- get s&p global evaluated prices.
- get terms conditions
- financial
- fixed income calculations.
- bond analytics
- run fi calculation
- get terms and conditions.
- s&p global evaluated prices.
- run fixed income calculation.
- optimize fi portfolio
- financial data
- batch fixed income analytics.
- fixed income terms and conditions.
- portfolio analytics
- get fixed income terms and conditions.
- get fi calc
- get evaluated prices.
- get terms
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
