---
consumed_apis:
- factset-formula
- factset-quant
- factset-qfl
- factset-screening
description: Unified workflow for quantitative research including formula-based data retrieval, screening, factor analysis, and quant engine computations. Used by quantitative analysts.
layout: capability
name: FactSet Quantitative Research
operations:
- description: Execute formula queries.
  method: GET
  name: list-formulas
  path: /v1/formulas
- description: List quant engine resources.
  method: GET
  name: list-quant
  path: /v1/quant-engine
- description: List factor library resources.
  method: GET
  name: list-factors
  path: /v1/factors
- description: List screening resources.
  method: GET
  name: list-screens
  path: /v1/screens
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- get factor library data.
- formula-based data retrieval.
- quant engine computations.
- universal screening.
- market data
- screening
- factset
- list factors
- list screens
- portfolio analytics
- list screening resources.
- list factor library resources.
- run formula
- investment analytics
- research
- run quant engine
- run universal screening.
- execute formula queries.
- quantitative research
- list quant
- run quant engine computations.
- factor library data.
- financial data
- factor analysis
- financial
- list quant engine resources.
- run screen
- list formulas
- get factors
slug: quantitative-research
tags:
- FactSet
- Quantitative Research
- Factor Analysis
- Screening
tools:
- description: Execute formula queries.
  hints:
    openWorld: true
    readOnly: true
  name: run-formula
- description: Run quant engine computations.
  hints:
    openWorld: true
    readOnly: true
  name: run-quant-engine
- description: Get factor library data.
  hints:
    openWorld: true
    readOnly: true
  name: get-factors
- description: Run universal screening.
  hints:
    openWorld: true
    readOnly: true
  name: run-screen
---
