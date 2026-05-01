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
- financial
- list metadata
- list portfolio metadata
- performance attribution
- vault resources.
- investment analytics
- list portfolios.
- list pa engine
- list portfolio metadata.
- market data
- portfolio resources.
- financial data
- list spar engine resources.
- list spar engine
- spar engine resources.
- pa engine resources.
- factset
- portfolio analytics
- list publisher resources.
- list vault
- list analytics datastore.
- risk analysis
- list datastore
- list vault resources.
- list analytics datastore
- list portfolios
- research
- list spar
- portfolio metadata.
- list publisher
- list pa engine resources.
- analytics datastore.
- list pa
slug: portfolio-analytics
source_filename: portfolio-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"FactSet Portfolio Analytics\"\n  description: \"Unified workflow for portfolio analytics including performance attribution, risk analysis, and benchmarking. Used by portfolio managers and performance analysts.\"\n  tags:\n    - FactSet\n    - Portfolio Analytics\n    - Performance Attribution\n    - Risk Analysis\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTSET_USERNAME: FACTSET_USERNAME\n      FACTSET_PASSWORD: FACTSET_PASSWORD\n\ncapability:\n  consumes:\n    - import: factset-pa-engine\n      location: ./shared/pa-engine.yaml\n    - import: factset-spar\n      location: ./shared/spar-engine.yaml\n    - import: factset-vault\n      location: ./shared/vault.yaml\n    - import: factset-publisher\n      location: ./shared/publisher.yaml\n    - import: factset-portfolio\n      location: ./shared/portfolio.yaml\n    - import: factset-portfolio-meta\n      location: ./shared/portfolio-metadata.yaml\n\
  \    - import: factset-datastore\n      location: ./shared/analytics-datastore.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: portfolio-analytics-api\n      description: \"Unified REST API for FactSet portfolio analytics.\"\n      resources:\n        - path: /v1/pa-engine\n          name: pa-engine\n          description: \"PA Engine resources.\"\n          operations:\n            - method: GET\n              name: list-pa\n              description: \"List PA Engine resources.\"\n              call: \"factset-pa-engine.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/spar-engine\n          name: spar-engine\n          description: \"SPAR Engine resources.\"\n          operations:\n            - method: GET\n              name: list-spar\n              description: \"List SPAR Engine resources.\"\n              call: \"factset-spar.list\"\n              outputParameters:\n        \
  \        - type: object\n                  mapping: \"$.\"\n        - path: /v1/vault\n          name: vault\n          description: \"Vault resources.\"\n          operations:\n            - method: GET\n              name: list-vault\n              description: \"List Vault resources.\"\n              call: \"factset-vault.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/portfolios\n          name: portfolios\n          description: \"Portfolio resources.\"\n          operations:\n            - method: GET\n              name: list-portfolios\n              description: \"List portfolios.\"\n              call: \"factset-portfolio.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/portfolio-metadata\n          name: portfolio-metadata\n          description: \"Portfolio metadata.\"\n          operations:\n            - method: GET\n\
  \              name: list-metadata\n              description: \"List portfolio metadata.\"\n              call: \"factset-portfolio-meta.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analytics-datastore\n          name: analytics-datastore\n          description: \"Analytics datastore.\"\n          operations:\n            - method: GET\n              name: list-datastore\n              description: \"List analytics datastore.\"\n              call: \"factset-datastore.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: portfolio-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted portfolio analytics.\"\n      tools:\n        - name: list-pa-engine\n          description: \"List PA Engine resources.\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"factset-pa-engine.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-spar-engine\n          description: \"List SPAR Engine resources.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"factset-spar.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-vault\n          description: \"List Vault resources.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"factset-vault.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-publisher\n          description: \"List Publisher resources.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"factset-publisher.list\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: list-portfolios\n          description: \"List portfolios.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"factset-portfolio.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-portfolio-metadata\n          description: \"List portfolio metadata.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"factset-portfolio-meta.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-analytics-datastore\n          description: \"List analytics datastore.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"factset-datastore.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
