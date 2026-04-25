---
consumed_apis:
- factset-ofdb
- factset-sdf
- factset-cfd
- factset-xdf-model
- factset-xdf-entire
- factset-xdf-symbol
- factset-dst
- factset-prog
- factset-prb
description: Unified workflow for data management including custom databases, standard datafeeds, exchange datafeeds, content feeds, and programmatic environments. Used by data engineers.
layout: capability
name: FactSet Data Management
operations:
- description: List databases.
  method: GET
  name: list-databases
  path: /v1/databases
- description: List datafeeds.
  method: GET
  name: list-datafeeds
  path: /v1/datafeeds
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- get direct streaming data.
- list ofdb databases.
- financial data
- get standard datafeed
- get content feeds dictionary.
- get xdf model
- data management
- get xdf snapshot
- list ofdb
- get exchange datafeed model.
- research
- get programmatic environment.
- datafeed
- ofdb database management.
- get streaming
- get standard datafeed.
- market data
- list datafeeds.
- etl
- investment analytics
- factset
- list databases.
- get prog env
- list databases
- portfolio analytics
- get exchange datafeed snapshot.
- get content feeds
- standard datafeed.
- list datafeeds
- financial
slug: data-management
tags:
- FactSet
- Data Management
- Datafeed
- ETL
tools:
- description: List OFDB databases.
  hints:
    readOnly: true
  name: list-ofdb
- description: Get standard datafeed.
  hints:
    readOnly: true
  name: get-standard-datafeed
- description: Get content feeds dictionary.
  hints:
    readOnly: true
  name: get-content-feeds
- description: Get exchange datafeed model.
  hints:
    readOnly: true
  name: get-xdf-model
- description: Get exchange datafeed snapshot.
  hints:
    readOnly: true
  name: get-xdf-snapshot
- description: Get direct streaming data.
  hints:
    readOnly: true
  name: get-streaming
- description: Get programmatic environment.
  hints:
    readOnly: true
  name: get-prog-env
---
