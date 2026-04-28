---
categories: []
consumed_apis:
- factset-optimizer
- factset-axioma-eq
- factset-barra
- factset-northfield
- factset-open-risk
description: Unified workflow for portfolio optimization using multiple optimization engines including FactSet, Axioma, Barra, Northfield, and open risk models. Used by portfolio optimizers.
layout: capability
name: FactSet Portfolio Optimization
operations:
- description: List optimizations.
  method: GET
  name: list-optimizations
  path: /v1/optimize
- description: List risk models.
  method: GET
  name: list-risk-models
  path: /v1/risk-models
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- investment analytics
- run northfield optimization.
- factset optimize
- list risk models
- research
- asset allocation
- run factset portfolio optimization.
- factset
- run barra optimization.
- market data
- risk models
- get risk models
- portfolio optimization
- list optimizations
- financial
- get open risk models.
- northfield optimize
- barra optimize
- list optimizations.
- list risk models.
- financial data
- portfolio optimization.
- axioma equity optimize
- run axioma equity optimization.
- portfolio analytics
- open risk models.
slug: portfolio-optimization
tags:
- FactSet
- Portfolio Optimization
- Risk Models
- Asset Allocation
tools:
- description: Run FactSet portfolio optimization.
  hints:
    readOnly: true
  name: factset-optimize
- description: Run Axioma equity optimization.
  hints:
    readOnly: true
  name: axioma-equity-optimize
- description: Run Barra optimization.
  hints:
    readOnly: true
  name: barra-optimize
- description: Run Northfield optimization.
  hints:
    readOnly: true
  name: northfield-optimize
- description: Get open risk models.
  hints:
    readOnly: true
  name: get-risk-models
---
