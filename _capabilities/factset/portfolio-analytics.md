---
categories: []
consumed_apis: []
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
- analytics datastore.
- performance attribution
- list vault resources.
- portfolio metadata.
- list analytics datastore.
- factset
- portfolio analytics
- list spar
- risk analysis
- list pa
- list publisher
- list portfolios
- financial data
- research
- list pa engine resources.
- list analytics datastore
- list spar engine resources.
- list datastore
- list portfolio metadata.
- spar engine resources.
- list metadata
- pa engine resources.
- list publisher resources.
- financial
- list portfolio metadata
- list portfolios.
- market data
- vault resources.
- list vault
- list pa engine
- list spar engine
- portfolio resources.
- investment analytics
slug: portfolio-analytics
source_filename: portfolio-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FactSet Portfolio Analytics\n  description: Unified workflow for portfolio analytics including performance attribution, risk analysis, and benchmarking.\n    Used by portfolio managers and performance analysts.\n  tags:\n  - FactSet\n  - Portfolio Analytics\n  - Performance Attribution\n  - Risk Analysis\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACTSET_USERNAME: FACTSET_USERNAME\n    FACTSET_PASSWORD: FACTSET_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: factset-pa-engine\n    baseUri: https://api.factset.com\n    description: Portfolio analytics engine for multi-asset class performance, attribution, and risk.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: pa_engine\n      path: /\n      description: PA Engine API resources.\n      operations:\n      - name: list-pa-engine\n\
  \        method: GET\n        description: List PA Engine resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password:\
  \ '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri:\
  \ https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: portfolio-analytics-api\n    description: Unified REST API for FactSet portfolio analytics.\n    resources:\n    - path: /v1/pa-engine\n      name: pa-engine\n      description: PA Engine resources.\n      operations:\n      - method: GET\n        name:\
  \ list-pa\n        description: List PA Engine resources.\n        call: factset-pa-engine.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spar-engine\n      name: spar-engine\n      description: SPAR Engine resources.\n      operations:\n      - method: GET\n        name: list-spar\n        description: List SPAR Engine resources.\n        call: factset-spar.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vault\n      name: vault\n      description: Vault resources.\n      operations:\n      - method: GET\n        name: list-vault\n        description: List Vault resources.\n        call: factset-vault.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolios\n      name: portfolios\n      description: Portfolio resources.\n      operations:\n      - method: GET\n        name: list-portfolios\n        description: List portfolios.\n        call:\
  \ factset-portfolio.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portfolio-metadata\n      name: portfolio-metadata\n      description: Portfolio metadata.\n      operations:\n      - method: GET\n        name: list-metadata\n        description: List portfolio metadata.\n        call: factset-portfolio-meta.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics-datastore\n      name: analytics-datastore\n      description: Analytics datastore.\n      operations:\n      - method: GET\n        name: list-datastore\n        description: List analytics datastore.\n        call: factset-datastore.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: portfolio-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted portfolio analytics.\n    tools:\n    - name: list-pa-engine\n      description: List\
  \ PA Engine resources.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factset-pa-engine.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-spar-engine\n      description: List SPAR Engine resources.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factset-spar.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vault\n      description: List Vault resources.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factset-vault.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-publisher\n      description: List Publisher resources.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factset-publisher.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-portfolios\n      description: List portfolios.\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: factset-portfolio.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-portfolio-metadata\n      description: List portfolio metadata.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factset-portfolio-meta.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-analytics-datastore\n      description: List analytics datastore.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factset-datastore.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/portfolio-analytics.yaml
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
