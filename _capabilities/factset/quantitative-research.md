---
categories: []
consumed_apis: []
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
- list quant
- execute formula queries.
- research
- investment analytics
- market data
- quant engine computations.
- formula-based data retrieval.
- list factor library resources.
- list screens
- portfolio analytics
- list quant engine resources.
- factset
- run universal screening.
- quantitative research
- screening
- list formulas
- get factors
- financial data
- list screening resources.
- factor analysis
- run screen
- run quant engine
- financial
- list factors
- universal screening.
- factor library data.
- get factor library data.
- run formula
- run quant engine computations.
slug: quantitative-research
source_filename: quantitative-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FactSet Quantitative Research\n  description: Unified workflow for quantitative research including formula-based data retrieval, screening, factor analysis,\n    and quant engine computations. Used by quantitative analysts.\n  tags:\n  - FactSet\n  - Quantitative Research\n  - Factor Analysis\n  - Screening\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACTSET_USERNAME: FACTSET_USERNAME\n    FACTSET_PASSWORD: FACTSET_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: factset-formula\n    baseUri: https://api.factset.com/formula-api\n    description: Flexible formula-based API for accessing FactSet data via FQL and Screening.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: formula\n      path: /\n      description: Formula API resources.\n      operations:\n      - name: list-formula\n\
  \        method: GET\n        description: List Formula resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password:\
  \ '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace:\
  \ quant-research-api\n    description: Unified REST API for quantitative research.\n    resources:\n    - path: /v1/formulas\n      name: formulas\n      description: Formula-based data retrieval.\n      operations:\n      - method: GET\n        name: list-formulas\n        description: Execute formula queries.\n        call: factset-formula.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quant-engine\n      name: quant-engine\n      description: Quant engine computations.\n      operations:\n      - method: GET\n        name: list-quant\n        description: List quant engine resources.\n        call: factset-quant.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/factors\n      name: factors\n      description: Factor library data.\n      operations:\n      - method: GET\n        name: list-factors\n        description: List factor library resources.\n        call: factset-qfl.list\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/screens\n      name: screens\n      description: Universal screening.\n      operations:\n      - method: GET\n        name: list-screens\n        description: List screening resources.\n        call: factset-screening.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: quant-research-mcp\n    transport: http\n    description: MCP server for AI-assisted quantitative research.\n    tools:\n    - name: run-formula\n      description: Execute formula queries.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factset-formula.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-quant-engine\n      description: Run quant engine computations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factset-quant.list\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-factors\n      description: Get factor library data.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factset-qfl.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-screen\n      description: Run universal screening.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factset-screening.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
