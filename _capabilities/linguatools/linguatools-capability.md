---
categories: []
consumed_apis: []
description: The Linguatools Collocations API provides access to a dictionary of more than 2 million English collocations. It returns collocations for a query word filtered by syntactic relation, part of speech, and a minimum significance score, with up to three example sentences per collocation. The API is distributed via RapidAPI.
layout: capability
name: Linguatools Collocations API
operations:
- description: Get collocations for a word
  method: GET
  name: getcollocations
  path: /
personas: []
provider_name: Linguatools
provider_slug: linguatools
search_terms:
- english
- api
- dictionary
- nlp
- get collocations for a word
- language
- getcollocations
- linguatools
- collocations
- linguistics
slug: linguatools-capability
source_filename: linguatools-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Linguatools Collocations API\n  description: The Linguatools Collocations API provides access to a dictionary of more than 2 million English collocations.\n    It returns collocations for a query word filtered by syntactic relation, part of speech, and a minimum significance score,\n    with up to three example sentences per collocation. The API is distributed via RapidAPI.\n  tags:\n  - Linguatools\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: linguatools\n    baseUri: https://linguatools-collocations.p.rapidapi.com\n    description: Linguatools Collocations API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-RapidAPI-Key\n      value: '{{LINGUATOOLS_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: getcollocations\n        method: GET\n        description: Get collocations for a word\n\
  \        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: The query word (case-insensitive).\n        - name: lang\n          in: query\n          type: string\n          required: true\n          description: ISO 639-1 language code. Currently only `en` is supported.\n        - name: relation\n          in: query\n          type: string\n          description: 'Syntactic relation type (case-sensitive). Examples include `V:obj:N` (verb-object), `N:mod:Adj` (noun-adjective\n            modifier), `Adj:mod:N`, `V:subj:N`, `N:prep:N`, '\n        - name: min_sig\n          in: query\n          type: integer\n          description: Minimum significance threshold. Values must be 100 or greater.\n        - name: pos\n          in: query\n          type: string\n          description: Part of speech filter (v2 only). One of `V` (verb), `Vinf` (infinitive verb), `N` (noun), `Adj` (adjective),\n            `Adv`\
  \ (adverb).\n        - name: X-RapidAPI-Key\n          in: header\n          type: string\n          required: true\n          description: Your RapidAPI subscription key.\n        - name: X-RapidAPI-Host\n          in: header\n          type: string\n          required: true\n          description: Must be set to `linguatools-collocations.p.rapidapi.com`.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: linguatools-rest\n    description: REST adapter for Linguatools Collocations API.\n    resources:\n    - path: /\n      name: getcollocations\n      operations:\n      - method: GET\n        name: getcollocations\n        description: Get collocations for a word\n        call: linguatools.getcollocations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: linguatools-mcp\n    transport:\
  \ http\n    description: MCP adapter for Linguatools Collocations API for AI agent use.\n    tools:\n    - name: getcollocations\n      description: Get collocations for a word\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: linguatools.getcollocations\n      with:\n        query: tools.query\n        lang: tools.lang\n        relation: tools.relation\n        min_sig: tools.min_sig\n        pos: tools.pos\n      inputParameters:\n      - name: query\n        type: string\n        description: The query word (case-insensitive).\n        required: true\n      - name: lang\n        type: string\n        description: ISO 639-1 language code. Currently only `en` is supported.\n        required: true\n      - name: relation\n        type: string\n        description: 'Syntactic relation type (case-sensitive). Examples include `V:obj:N` (verb-object), `N:mod:Adj` (noun-adjective\n          modifier), `Adj:mod:N`, `V:subj:N`, `N:prep:N`,\
  \ '\n      - name: min_sig\n        type: integer\n        description: Minimum significance threshold. Values must be 100 or greater.\n      - name: pos\n        type: string\n        description: Part of speech filter (v2 only). One of `V` (verb), `Vinf` (infinitive verb), `N` (noun), `Adj` (adjective),\n          `Adv` (adverb).\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LINGUATOOLS_TOKEN: LINGUATOOLS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linguatools/refs/heads/main/capabilities/linguatools-capability.yaml
tags:
- Linguatools
- API
tools:
- description: Get collocations for a word
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcollocations
---
