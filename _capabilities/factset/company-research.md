---
consumed_apis:
- factset-entity
- factset-fundamentals
- factset-people
- factset-concordance
- factset-symbology
- factset-classifications
- factset-rbics
- factset-esg
- factset-ownership
- factset-georev
- factset-id-lookup
description: Unified workflow for company research including entity data, fundamentals, people, concordance, symbology, classifications, ESG, and ownership. Used by research analysts.
layout: capability
name: FactSet Company Research
operations:
- description: Get entity data.
  method: GET
  name: get-entities
  path: /v1/entities
- description: Get fundamentals.
  method: GET
  name: get-fundamentals
  path: /v1/fundamentals
- description: Get people data.
  method: GET
  name: get-people
  path: /v1/people
- description: Concordance lookup.
  method: GET
  name: concord
  path: /v1/concordance
- description: Get ESG data.
  method: GET
  name: get-esg
  path: /v1/esg
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- people data.
- concordance lookup
- get people data.
- get ownership data.
- entity concordance.
- get esg scores.
- get geographic revenue.
- financial data
- get rbics classifications.
- translate between identifier types.
- get georev
- company research
- get fundamentals.
- fundamental data.
- get entity reference data.
- research
- concordance entity lookup.
- get esg data.
- get entity data.
- concordance lookup.
- get fundamentals
- esg data.
- fundamentals
- entity data.
- get entities
- concord
- market data
- get fundamental financial data.
- get industry classifications.
- get people profiles.
- investment analytics
- look up security identifiers.
- factset
- get classifications
- get esg
- get rbics
- id lookup
- get people
- portfolio analytics
- get entity
- symbology translate
- get ownership
- financial
- entity data
slug: company-research
tags:
- FactSet
- Company Research
- Entity Data
- Fundamentals
tools:
- description: Get entity reference data.
  hints:
    readOnly: true
  name: get-entity
- description: Get fundamental financial data.
  hints:
    readOnly: true
  name: get-fundamentals
- description: Get people profiles.
  hints:
    readOnly: true
  name: get-people
- description: Concordance entity lookup.
  hints:
    readOnly: true
  name: concordance-lookup
- description: Translate between identifier types.
  hints:
    readOnly: true
  name: symbology-translate
- description: Get industry classifications.
  hints:
    readOnly: true
  name: get-classifications
- description: Get RBICS classifications.
  hints:
    readOnly: true
  name: get-rbics
- description: Get ESG scores.
  hints:
    readOnly: true
  name: get-esg
- description: Get ownership data.
  hints:
    readOnly: true
  name: get-ownership
- description: Get geographic revenue.
  hints:
    readOnly: true
  name: get-georev
- description: Look up security identifiers.
  hints:
    readOnly: true
  name: id-lookup
---
