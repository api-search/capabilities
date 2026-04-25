---
consumed_apis:
- factset-pa-engine
- factset-spar
- factset-vault
- factset-publisher
- factset-portfolio
- factset-portfolio-meta
- factset-datastore
description: Unified workflow for portfolio analytics including performance attribution, risk analysis, and benchmarking. Used by portfolio managers and performance analysts.
layout: capability
name: FactSet Portfolio Analytics
operations:
- description: List PA Engine resources.
  method: GET
  name: list-pa
  path: /v1/pa-engine
- description: List SPAR Engine resources.
  method: GET
  name: list-spar
  path: /v1/spar-engine
- description: List Vault resources.
  method: GET
  name: list-vault
  path: /v1/vault
- description: List portfolios.
  method: GET
  name: list-portfolios
  path: /v1/portfolios
- description: List portfolio metadata.
  method: GET
  name: list-metadata
  path: /v1/portfolio-metadata
- description: List analytics datastore.
  method: GET
  name: list-datastore
  path: /v1/analytics-datastore
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- risk analysis
- list pa engine
- list portfolio metadata
- spar engine resources.
- list portfolios.
- list datastore
- financial data
- list analytics datastore.
- list spar engine
- portfolio analytics
- portfolio metadata.
- list portfolio metadata.
- list publisher resources.
- financial
- market data
- list spar engine resources.
- list publisher
- list portfolios
- research
- pa engine resources.
- list pa engine resources.
- list vault resources.
- vault resources.
- performance attribution
- list vault
- list pa
- investment analytics
- factset
- list spar
- list analytics datastore
- analytics datastore.
- portfolio resources.
- list metadata
slug: portfolio-analytics
tags:
- FactSet
- Portfolio Analytics
- Performance Attribution
- Risk Analysis
tools:
- description: List PA Engine resources.
  hints:
    openWorld: true
    readOnly: true
  name: list-pa-engine
- description: List SPAR Engine resources.
  hints:
    openWorld: true
    readOnly: true
  name: list-spar-engine
- description: List Vault resources.
  hints:
    openWorld: true
    readOnly: true
  name: list-vault
- description: List Publisher resources.
  hints:
    openWorld: true
    readOnly: true
  name: list-publisher
- description: List portfolios.
  hints:
    openWorld: true
    readOnly: true
  name: list-portfolios
- description: List portfolio metadata.
  hints:
    openWorld: true
    readOnly: true
  name: list-portfolio-metadata
- description: List analytics datastore.
  hints:
    openWorld: true
    readOnly: true
  name: list-analytics-datastore
---
