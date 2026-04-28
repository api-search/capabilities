---
categories: []
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
- investment analytics
- list analytics datastore
- list portfolios
- list pa engine
- list pa engine resources.
- list portfolio metadata
- research
- list publisher resources.
- factset
- list pa
- list analytics datastore.
- market data
- list metadata
- financial
- spar engine resources.
- list portfolios.
- analytics datastore.
- list publisher
- list spar engine resources.
- list spar engine
- portfolio resources.
- list datastore
- list portfolio metadata.
- portfolio metadata.
- risk analysis
- list spar
- financial data
- portfolio analytics
- list vault resources.
- pa engine resources.
- performance attribution
- list vault
- vault resources.
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
