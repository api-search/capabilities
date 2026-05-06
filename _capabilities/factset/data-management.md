---
categories:
- data-engineering
consumed_apis: []
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
- standard datafeed.
- get direct streaming data.
- list databases.
- list ofdb databases.
- research
- get exchange datafeed model.
- list datafeeds.
- investment analytics
- market data
- get content feeds dictionary.
- list datafeeds
- etl
- portfolio analytics
- get standard datafeed.
- get content feeds
- factset
- datafeed
- ofdb database management.
- get exchange datafeed snapshot.
- get prog env
- get streaming
- financial data
- data management
- get xdf model
- get programmatic environment.
- list databases
- financial
- get xdf snapshot
- get standard datafeed
- list ofdb
slug: data-management
source_filename: data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FactSet Data Management\n  description: Unified workflow for data management including custom databases, standard datafeeds, exchange datafeeds, content\n    feeds, and programmatic environments. Used by data engineers.\n  tags:\n  - FactSet\n  - Data Management\n  - Datafeed\n  - ETL\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACTSET_USERNAME: FACTSET_USERNAME\n    FACTSET_PASSWORD: FACTSET_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: factset-ofdb\n    baseUri: https://api.factset.com\n    description: Open FactSet Database for creating and managing non-portfolio databases.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: ofdb\n      path: /\n      description: OFDB API resources.\n      operations:\n      - name: list-ofdb\n        method: GET\n        description: List\
  \ OFDB resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    -\
  \ name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description:\
  \ Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n   \
  \   operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8090\n    namespace: data-management-api\n    description: Unified REST API for data management.\n    resources:\n    - path: /v1/databases\n\
  \      name: databases\n      description: OFDB database management.\n      operations:\n      - method: GET\n        name: list-databases\n        description: List databases.\n        call: factset-ofdb.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datafeeds\n      name: datafeeds\n      description: Standard datafeed.\n      operations:\n      - method: GET\n        name: list-datafeeds\n        description: List datafeeds.\n        call: factset-sdf.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: data-management-mcp\n    transport: http\n    description: MCP server for AI-assisted data management.\n    tools:\n    - name: list-ofdb\n      description: List OFDB databases.\n      hints:\n        readOnly: true\n      call: factset-ofdb.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-standard-datafeed\n      description:\
  \ Get standard datafeed.\n      hints:\n        readOnly: true\n      call: factset-sdf.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-feeds\n      description: Get content feeds dictionary.\n      hints:\n        readOnly: true\n      call: factset-cfd.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-xdf-model\n      description: Get exchange datafeed model.\n      hints:\n        readOnly: true\n      call: factset-xdf-model.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-xdf-snapshot\n      description: Get exchange datafeed snapshot.\n      hints:\n        readOnly: true\n      call: factset-xdf-entire.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-streaming\n      description: Get direct streaming data.\n      hints:\n        readOnly: true\n      call: factset-dst.list\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-prog-env\n      description: Get programmatic environment.\n      hints:\n        readOnly: true\n      call: factset-prog.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
