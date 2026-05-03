---
categories: []
consumed_apis:
- factset-entity
- factset-fundamentals
- factset-people
- factset-concordance
- factset-symbology
- factset-classifications
- factset-rbics
- factset-esg
- factset-ownership
- factset-georev
- factset-id-lookup
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
- people data.
- get entity reference data.
- look up security identifiers.
- concord
- concordance lookup
- concordance lookup.
- financial
- get classifications
- id lookup
- factset
- get people profiles.
- get fundamentals
- esg data.
- fundamental data.
- concordance entity lookup.
- get esg scores.
- get georev
- get rbics
- entity concordance.
- get esg
- get ownership
- research
- market data
- entity data.
- get entity
- get entities
- fundamentals
- financial data
- entity data
- get industry classifications.
- get entity data.
- portfolio analytics
- get fundamental financial data.
- symbology translate
- get ownership data.
- translate between identifier types.
- investment analytics
- get fundamentals.
- company research
- get people data.
- get esg data.
- get geographic revenue.
- get rbics classifications.
- get people
slug: company-research
source_filename: company-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"FactSet Company Research\"\n  description: \"Unified workflow for company research including entity data, fundamentals, people, concordance, symbology, classifications, ESG, and ownership. Used by research analysts.\"\n  tags:\n    - FactSet\n    - Company Research\n    - Entity Data\n    - Fundamentals\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTSET_USERNAME: FACTSET_USERNAME\n      FACTSET_PASSWORD: FACTSET_PASSWORD\n\ncapability:\n  consumes:\n    - import: factset-entity\n      location: ./shared/entity.yaml\n    - import: factset-fundamentals\n      location: ./shared/fundamentals.yaml\n    - import: factset-people\n      location: ./shared/people.yaml\n    - import: factset-concordance\n      location: ./shared/concordance.yaml\n    - import: factset-symbology\n      location: ./shared/symbology.yaml\n    - import: factset-classifications\n      location: ./shared/classifications.yaml\n\
  \    - import: factset-rbics\n      location: ./shared/rbics.yaml\n    - import: factset-esg\n      location: ./shared/esg.yaml\n    - import: factset-ownership\n      location: ./shared/ownership.yaml\n    - import: factset-georev\n      location: ./shared/georev.yaml\n    - import: factset-id-lookup\n      location: ./shared/id-lookup.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: company-research-api\n      description: \"Unified REST API for company research.\"\n      resources:\n        - path: /v1/entities\n          name: entities\n          description: \"Entity data.\"\n          operations:\n            - method: GET\n              name: get-entities\n              description: \"Get entity data.\"\n              call: \"factset-entity.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/fundamentals\n          name: fundamentals\n          description: \"Fundamental data.\"\n\
  \          operations:\n            - method: GET\n              name: get-fundamentals\n              description: \"Get fundamentals.\"\n              call: \"factset-fundamentals.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/people\n          name: people\n          description: \"People data.\"\n          operations:\n            - method: GET\n              name: get-people\n              description: \"Get people data.\"\n              call: \"factset-people.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/concordance\n          name: concordance\n          description: \"Entity concordance.\"\n          operations:\n            - method: GET\n              name: concord\n              description: \"Concordance lookup.\"\n              call: \"factset-concordance.list\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n        - path: /v1/esg\n          name: esg\n          description: \"ESG data.\"\n          operations:\n            - method: GET\n              name: get-esg\n              description: \"Get ESG data.\"\n              call: \"factset-esg.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9083\n      namespace: company-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted company research.\"\n      tools:\n        - name: get-entity\n          description: \"Get entity reference data.\"\n          hints:\n            readOnly: true\n          call: \"factset-entity.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-fundamentals\n          description: \"Get fundamental financial data.\"\n          hints:\n            readOnly: true\n          call: \"\
  factset-fundamentals.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-people\n          description: \"Get people profiles.\"\n          hints:\n            readOnly: true\n          call: \"factset-people.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: concordance-lookup\n          description: \"Concordance entity lookup.\"\n          hints:\n            readOnly: true\n          call: \"factset-concordance.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: symbology-translate\n          description: \"Translate between identifier types.\"\n          hints:\n            readOnly: true\n          call: \"factset-symbology.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-classifications\n          description: \"Get industry classifications.\"\
  \n          hints:\n            readOnly: true\n          call: \"factset-classifications.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-rbics\n          description: \"Get RBICS classifications.\"\n          hints:\n            readOnly: true\n          call: \"factset-rbics.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-esg\n          description: \"Get ESG scores.\"\n          hints:\n            readOnly: true\n          call: \"factset-esg.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-ownership\n          description: \"Get ownership data.\"\n          hints:\n            readOnly: true\n          call: \"factset-ownership.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-georev\n          description: \"Get geographic\
  \ revenue.\"\n          hints:\n            readOnly: true\n          call: \"factset-georev.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: id-lookup\n          description: \"Look up security identifiers.\"\n          hints:\n            readOnly: true\n          call: \"factset-id-lookup.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
