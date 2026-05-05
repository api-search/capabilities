---
categories: []
consumed_apis:
- factset-formula
- factset-quant
- factset-qfl
- factset-screening
description: Unified workflow for quantitative research including formula-based data retrieval, screening, factor analysis, and quant engine computations. Used by quantitative analysts.
layout: capability
name: FactSet Quantitative Research
operations:
- description: Execute formula queries.
  method: GET
  name: list-formulas
  path: /v1/formulas
- description: List quant engine resources.
  method: GET
  name: list-quant
  path: /v1/quant-engine
- description: List factor library resources.
  method: GET
  name: list-factors
  path: /v1/factors
- description: List screening resources.
  method: GET
  name: list-screens
  path: /v1/screens
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- universal screening.
- list screens
- quant engine computations.
- market data
- research
- list factors
- run quant engine
- list factor library resources.
- investment analytics
- list screening resources.
- get factor library data.
- formula-based data retrieval.
- factor analysis
- execute formula queries.
- run quant engine computations.
- run formula
- financial
- get factors
- financial data
- run screen
- portfolio analytics
- factset
- factor library data.
- list quant
- screening
- list quant engine resources.
- list formulas
- run universal screening.
- quantitative research
slug: quantitative-research
source_filename: quantitative-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"FactSet Quantitative Research\"\n  description: \"Unified workflow for quantitative research including formula-based data retrieval, screening, factor analysis, and quant engine computations. Used by quantitative analysts.\"\n  tags:\n    - FactSet\n    - Quantitative Research\n    - Factor Analysis\n    - Screening\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTSET_USERNAME: FACTSET_USERNAME\n      FACTSET_PASSWORD: FACTSET_PASSWORD\n\ncapability:\n  consumes:\n    - import: factset-formula\n      location: ./shared/formula.yaml\n    - import: factset-quant\n      location: ./shared/quant-engine.yaml\n    - import: factset-qfl\n      location: ./shared/quant-factor-library.yaml\n    - import: factset-screening\n      location: ./shared/universal-screening.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: quant-research-api\n      description: \"\
  Unified REST API for quantitative research.\"\n      resources:\n        - path: /v1/formulas\n          name: formulas\n          description: \"Formula-based data retrieval.\"\n          operations:\n            - method: GET\n              name: list-formulas\n              description: \"Execute formula queries.\"\n              call: \"factset-formula.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/quant-engine\n          name: quant-engine\n          description: \"Quant engine computations.\"\n          operations:\n            - method: GET\n              name: list-quant\n              description: \"List quant engine resources.\"\n              call: \"factset-quant.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/factors\n          name: factors\n          description: \"Factor library data.\"\n          operations:\n\
  \            - method: GET\n              name: list-factors\n              description: \"List factor library resources.\"\n              call: \"factset-qfl.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/screens\n          name: screens\n          description: \"Universal screening.\"\n          operations:\n            - method: GET\n              name: list-screens\n              description: \"List screening resources.\"\n              call: \"factset-screening.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: quant-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted quantitative research.\"\n      tools:\n        - name: run-formula\n          description: \"Execute formula queries.\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"factset-formula.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-quant-engine\n          description: \"Run quant engine computations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"factset-quant.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-factors\n          description: \"Get factor library data.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"factset-qfl.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-screen\n          description: \"Run universal screening.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"factset-screening.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/quantitative-research.yaml
tags:
- FactSet
- Quantitative Research
- Factor Analysis
- Screening
tools:
- description: Execute formula queries.
  hints:
    openWorld: true
    readOnly: true
  name: run-formula
- description: Run quant engine computations.
  hints:
    openWorld: true
    readOnly: true
  name: run-quant-engine
- description: Get factor library data.
  hints:
    openWorld: true
    readOnly: true
  name: get-factors
- description: Run universal screening.
  hints:
    openWorld: true
    readOnly: true
  name: run-screen
---
