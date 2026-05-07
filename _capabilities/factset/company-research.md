---
categories: []
consumed_apis: []
description: Unified workflow for company research including entity data, fundamentals, people, concordance, symbology, classifications, ESG, and ownership. Used by research analysts.
layout: capability
name: FactSet Company Research
operations:
- description: Get entity data.
  method: GET
  name: get-entities
  path: /v1/entities
- description: Get fundamentals.
  method: GET
  name: get-fundamentals
  path: /v1/fundamentals
- description: Get people data.
  method: GET
  name: get-people
  path: /v1/people
- description: Concordance lookup.
  method: GET
  name: concord
  path: /v1/concordance
- description: Get ESG data.
  method: GET
  name: get-esg
  path: /v1/esg
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- get entity data.
- company research
- look up security identifiers.
- get esg data.
- get esg
- concord
- get ownership
- get fundamental financial data.
- factset
- fundamental data.
- portfolio analytics
- get geographic revenue.
- entity data.
- get entities
- fundamentals
- financial data
- research
- get fundamentals
- get entity
- entity concordance.
- get industry classifications.
- get entity reference data.
- get rbics classifications.
- id lookup
- get fundamentals.
- get rbics
- concordance lookup
- get people
- esg data.
- people data.
- entity data
- concordance lookup.
- financial
- symbology translate
- concordance entity lookup.
- market data
- translate between identifier types.
- get georev
- get ownership data.
- get people data.
- investment analytics
- get esg scores.
- get people profiles.
- get classifications
slug: company-research
source_filename: company-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FactSet Company Research\n  description: Unified workflow for company research including entity data, fundamentals, people, concordance, symbology,\n    classifications, ESG, and ownership. Used by research analysts.\n  tags:\n  - FactSet\n  - Company Research\n  - Entity Data\n  - Fundamentals\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACTSET_USERNAME: FACTSET_USERNAME\n    FACTSET_PASSWORD: FACTSET_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n    \
  \  path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n\
  \    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name:\
  \ list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n\
  \      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: factset-signals\n    baseUri: https://api.factset.com\n    description: Material event signals.\n    authentication:\n      type: basic\n      username: '{{FACTSET_USERNAME}}'\n      password: '{{FACTSET_PASSWORD}}'\n    resources:\n    - name: signals\n      path: /\n      description: Signals API resources.\n      operations:\n      - name: list-signals\n        method: GET\n        description: List Signals resources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n\
  \    namespace: company-research-api\n    description: Unified REST API for company research.\n    resources:\n    - path: /v1/entities\n      name: entities\n      description: Entity data.\n      operations:\n      - method: GET\n        name: get-entities\n        description: Get entity data.\n        call: factset-entity.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fundamentals\n      name: fundamentals\n      description: Fundamental data.\n      operations:\n      - method: GET\n        name: get-fundamentals\n        description: Get fundamentals.\n        call: factset-fundamentals.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/people\n      name: people\n      description: People data.\n      operations:\n      - method: GET\n        name: get-people\n        description: Get people data.\n        call: factset-people.list\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /v1/concordance\n      name: concordance\n      description: Entity concordance.\n      operations:\n      - method: GET\n        name: concord\n        description: Concordance lookup.\n        call: factset-concordance.list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/esg\n      name: esg\n      description: ESG data.\n      operations:\n      - method: GET\n        name: get-esg\n        description: Get ESG data.\n        call: factset-esg.list\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9083\n    namespace: company-research-mcp\n    transport: http\n    description: MCP server for AI-assisted company research.\n    tools:\n    - name: get-entity\n      description: Get entity reference data.\n      hints:\n        readOnly: true\n      call: factset-entity.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fundamentals\n\
  \      description: Get fundamental financial data.\n      hints:\n        readOnly: true\n      call: factset-fundamentals.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-people\n      description: Get people profiles.\n      hints:\n        readOnly: true\n      call: factset-people.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: concordance-lookup\n      description: Concordance entity lookup.\n      hints:\n        readOnly: true\n      call: factset-concordance.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: symbology-translate\n      description: Translate between identifier types.\n      hints:\n        readOnly: true\n      call: factset-symbology.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-classifications\n      description: Get industry classifications.\n      hints:\n        readOnly: true\n      call: factset-classifications.list\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rbics\n      description: Get RBICS classifications.\n      hints:\n        readOnly: true\n      call: factset-rbics.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-esg\n      description: Get ESG scores.\n      hints:\n        readOnly: true\n      call: factset-esg.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ownership\n      description: Get ownership data.\n      hints:\n        readOnly: true\n      call: factset-ownership.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-georev\n      description: Get geographic revenue.\n      hints:\n        readOnly: true\n      call: factset-georev.list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: id-lookup\n      description: Look up security identifiers.\n      hints:\n        readOnly: true\n  \
  \    call: factset-id-lookup.list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/company-research.yaml
tags:
- FactSet
- Company Research
- Entity Data
- Fundamentals
tools:
- description: Get entity reference data.
  hints:
    readOnly: true
  name: get-entity
- description: Get fundamental financial data.
  hints:
    readOnly: true
  name: get-fundamentals
- description: Get people profiles.
  hints:
    readOnly: true
  name: get-people
- description: Concordance entity lookup.
  hints:
    readOnly: true
  name: concordance-lookup
- description: Translate between identifier types.
  hints:
    readOnly: true
  name: symbology-translate
- description: Get industry classifications.
  hints:
    readOnly: true
  name: get-classifications
- description: Get RBICS classifications.
  hints:
    readOnly: true
  name: get-rbics
- description: Get ESG scores.
  hints:
    readOnly: true
  name: get-esg
- description: Get ownership data.
  hints:
    readOnly: true
  name: get-ownership
- description: Get geographic revenue.
  hints:
    readOnly: true
  name: get-georev
- description: Look up security identifiers.
  hints:
    readOnly: true
  name: id-lookup
---
