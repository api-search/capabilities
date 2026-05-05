---
categories: []
consumed_apis:
- factset-optimizer
- factset-axioma-eq
- factset-barra
- factset-northfield
- factset-open-risk
description: Unified workflow for portfolio optimization using multiple optimization engines including FactSet, Axioma, Barra, Northfield, and open risk models. Used by portfolio optimizers.
layout: capability
name: FactSet Portfolio Optimization
operations:
- description: List optimizations.
  method: GET
  name: list-optimizations
  path: /v1/optimize
- description: List risk models.
  method: GET
  name: list-risk-models
  path: /v1/risk-models
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- factset optimize
- get risk models
- list risk models.
- market data
- northfield optimize
- research
- barra optimize
- run axioma equity optimization.
- asset allocation
- investment analytics
- financial
- financial data
- risk models
- list optimizations.
- portfolio analytics
- list optimizations
- factset
- get open risk models.
- portfolio optimization
- portfolio optimization.
- open risk models.
- run northfield optimization.
- axioma equity optimize
- run factset portfolio optimization.
- run barra optimization.
- list risk models
slug: portfolio-optimization
source_filename: portfolio-optimization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"FactSet Portfolio Optimization\"\n  description: \"Unified workflow for portfolio optimization using multiple optimization engines including FactSet, Axioma, Barra, Northfield, and open risk models. Used by portfolio optimizers.\"\n  tags:\n    - FactSet\n    - Portfolio Optimization\n    - Risk Models\n    - Asset Allocation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTSET_USERNAME: FACTSET_USERNAME\n      FACTSET_PASSWORD: FACTSET_PASSWORD\n\ncapability:\n  consumes:\n    - import: factset-optimizer\n      location: ./shared/portfolio-optimizer.yaml\n    - import: factset-axioma-eq\n      location: ./shared/axioma-equity-optimizer.yaml\n    - import: factset-barra\n      location: ./shared/barra-portfolio-optimizer.yaml\n    - import: factset-northfield\n      location: ./shared/northfield-portfolio-optimizer.yaml\n    - import: factset-open-risk\n      location: ./shared/open-risk.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8085\n      namespace: portfolio-optimization-api\n      description: \"Unified REST API for portfolio optimization.\"\n      resources:\n        - path: /v1/optimize\n          name: optimize\n          description: \"Portfolio optimization.\"\n          operations:\n            - method: GET\n              name: list-optimizations\n              description: \"List optimizations.\"\n              call: \"factset-optimizer.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/risk-models\n          name: risk-models\n          description: \"Open risk models.\"\n          operations:\n            - method: GET\n              name: list-risk-models\n              description: \"List risk models.\"\n              call: \"factset-open-risk.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port:\
  \ 9085\n      namespace: portfolio-optimization-mcp\n      transport: http\n      description: \"MCP server for AI-assisted portfolio optimization.\"\n      tools:\n        - name: factset-optimize\n          description: \"Run FactSet portfolio optimization.\"\n          hints:\n            readOnly: true\n          call: \"factset-optimizer.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: axioma-equity-optimize\n          description: \"Run Axioma equity optimization.\"\n          hints:\n            readOnly: true\n          call: \"factset-axioma-eq.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: barra-optimize\n          description: \"Run Barra optimization.\"\n          hints:\n            readOnly: true\n          call: \"factset-barra.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: northfield-optimize\n\
  \          description: \"Run Northfield optimization.\"\n          hints:\n            readOnly: true\n          call: \"factset-northfield.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-risk-models\n          description: \"Get open risk models.\"\n          hints:\n            readOnly: true\n          call: \"factset-open-risk.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/portfolio-optimization.yaml
tags:
- FactSet
- Portfolio Optimization
- Risk Models
- Asset Allocation
tools:
- description: Run FactSet portfolio optimization.
  hints:
    readOnly: true
  name: factset-optimize
- description: Run Axioma equity optimization.
  hints:
    readOnly: true
  name: axioma-equity-optimize
- description: Run Barra optimization.
  hints:
    readOnly: true
  name: barra-optimize
- description: Run Northfield optimization.
  hints:
    readOnly: true
  name: northfield-optimize
- description: Get open risk models.
  hints:
    readOnly: true
  name: get-risk-models
---
