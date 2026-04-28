---
categories: []
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
- factset
- esg data.
- get esg scores.
- get esg
- concordance entity lookup.
- concord
- entity data
- get ownership
- investment analytics
- people data.
- entity data.
- concordance lookup.
- get georev
- portfolio analytics
- get fundamental financial data.
- get people profiles.
- translate between identifier types.
- financial data
- entity concordance.
- symbology translate
- fundamental data.
- get entity
- get geographic revenue.
- get entities
- financial
- get people
- get esg data.
- get industry classifications.
- get entity data.
- id lookup
- get classifications
- get ownership data.
- get fundamentals
- get entity reference data.
- concordance lookup
- get rbics classifications.
- fundamentals
- market data
- get rbics
- company research
- get fundamentals.
- get people data.
- research
- look up security identifiers.
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
