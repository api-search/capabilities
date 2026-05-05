---
categories:
- data-engineering
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
- get content feeds dictionary.
- market data
- get programmatic environment.
- get standard datafeed
- research
- standard datafeed.
- list databases.
- investment analytics
- financial
- financial data
- get streaming
- datafeed
- ofdb database management.
- list ofdb databases.
- get exchange datafeed snapshot.
- list datafeeds.
- portfolio analytics
- etl
- factset
- get direct streaming data.
- list databases
- get standard datafeed.
- data management
- get xdf snapshot
- get content feeds
- get xdf model
- list ofdb
- list datafeeds
- get exchange datafeed model.
- get prog env
slug: data-management
source_filename: data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"FactSet Data Management\"\n  description: \"Unified workflow for data management including custom databases, standard datafeeds, exchange datafeeds, content feeds, and programmatic environments. Used by data engineers.\"\n  tags:\n    - FactSet\n    - Data Management\n    - Datafeed\n    - ETL\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTSET_USERNAME: FACTSET_USERNAME\n      FACTSET_PASSWORD: FACTSET_PASSWORD\n\ncapability:\n  consumes:\n    - import: factset-ofdb\n      location: ./shared/ofdb.yaml\n    - import: factset-sdf\n      location: ./shared/standard-datafeed.yaml\n    - import: factset-cfd\n      location: ./shared/content-feeds-data-dictionary.yaml\n    - import: factset-xdf-model\n      location: ./shared/exchange-datafeed-data-model.yaml\n    - import: factset-xdf-entire\n      location: ./shared/exchange-datafeed-snapshot-api-entire-exchange.yaml\n   \
  \ - import: factset-xdf-symbol\n      location: ./shared/exchange-datafeed-snapshot-api-symbol-list.yaml\n    - import: factset-dst\n      location: ./shared/direct-streaming-of-transaction-messages.yaml\n    - import: factset-prog\n      location: ./shared/programmatic-environment.yaml\n    - import: factset-prb\n      location: ./shared/portfolio-reporting-batcher.yaml\n\n  exposes:\n    - type: rest\n      port: 8090\n      namespace: data-management-api\n      description: \"Unified REST API for data management.\"\n      resources:\n        - path: /v1/databases\n          name: databases\n          description: \"OFDB database management.\"\n          operations:\n            - method: GET\n              name: list-databases\n              description: \"List databases.\"\n              call: \"factset-ofdb.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/datafeeds\n          name: datafeeds\n         \
  \ description: \"Standard datafeed.\"\n          operations:\n            - method: GET\n              name: list-datafeeds\n              description: \"List datafeeds.\"\n              call: \"factset-sdf.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: data-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted data management.\"\n      tools:\n        - name: list-ofdb\n          description: \"List OFDB databases.\"\n          hints:\n            readOnly: true\n          call: \"factset-ofdb.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-standard-datafeed\n          description: \"Get standard datafeed.\"\n          hints:\n            readOnly: true\n          call: \"factset-sdf.list\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: get-content-feeds\n          description: \"Get content feeds dictionary.\"\n          hints:\n            readOnly: true\n          call: \"factset-cfd.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-xdf-model\n          description: \"Get exchange datafeed model.\"\n          hints:\n            readOnly: true\n          call: \"factset-xdf-model.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-xdf-snapshot\n          description: \"Get exchange datafeed snapshot.\"\n          hints:\n            readOnly: true\n          call: \"factset-xdf-entire.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-streaming\n          description: \"Get direct streaming data.\"\n          hints:\n            readOnly: true\n          call: \"factset-dst.list\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-prog-env\n          description: \"Get programmatic environment.\"\n          hints:\n            readOnly: true\n          call: \"factset-prog.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/data-management.yaml
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
