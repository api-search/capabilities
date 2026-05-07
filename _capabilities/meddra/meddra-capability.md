---
categories: []
consumed_apis: []
description: MedDRA (Medical Dictionary for Regulatory Activities) and the WHO Drug Dictionary provide standardized medical terminology APIs for adverse event coding, drug safety reporting, and pharmacovigilance. APIs enable term lookup, hierarchy navigation, and coding validation for regulatory submissions to ICH, FDA, EMA, and other health authorities.
layout: capability
name: MedDRA Medical Dictionary for Regulatory Activities API
operations:
- description: Search MedDRA terms
  method: GET
  name: searchterms
  path: /terms/search
- description: Get a term by code
  method: GET
  name: getterm
  path: /terms/{termCode}
- description: Get child terms in hierarchy
  method: GET
  name: gettermchildren
  path: /hierarchy/{level}/{code}/children
- description: Get parent terms in hierarchy
  method: GET
  name: gettermparents
  path: /hierarchy/{level}/{code}/parents
- description: List all System Organ Classes
  method: GET
  name: listsoc
  path: /soc
- description: Validate a MedDRA code
  method: POST
  name: validatecode
  path: /validate/code
- description: List available MedDRA versions
  method: GET
  name: listversions
  path: /versions
personas: []
provider_name: meddra
provider_slug: meddra
search_terms:
- get a term by code
- list all system organ classes
- validatecode
- meddra
- search meddra terms
- gettermchildren
- gettermparents
- get child terms in hierarchy
- validate a meddra code
- listsoc
- listversions
- list available meddra versions
- getterm
- api
- searchterms
- get parent terms in hierarchy
slug: meddra-capability
source_filename: meddra-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: MedDRA Medical Dictionary for Regulatory Activities API\n  description: MedDRA (Medical Dictionary for Regulatory Activities) and the WHO Drug Dictionary provide standardized medical\n    terminology APIs for adverse event coding, drug safety reporting, and pharmacovigilance. APIs enable term lookup, hierarchy\n    navigation, and coding validation for regulatory submissions to ICH, FDA, EMA, and other health authorities.\n  tags:\n  - Meddra\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: meddra\n    baseUri: https://api.meddra.example.com/v1\n    description: MedDRA Medical Dictionary for Regulatory Activities API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{MEDDRA_TOKEN}}'\n    resources:\n    - name: terms-search\n      path: /terms/search\n      operations:\n      - name: searchterms\n        method:\
  \ GET\n        description: Search MedDRA terms\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search text (partial match supported)\n        - name: level\n          in: query\n          type: string\n          description: MedDRA hierarchy level to search\n        - name: version\n          in: query\n          type: string\n          description: MedDRA version (e.g., 27.0); defaults to current\n        - name: language\n          in: query\n          type: string\n          description: Language for term text (en, ja, de, fr, es, zh, etc.)\n        - name: currentOnly\n          in: query\n          type: boolean\n          description: Return only current (non-deprecated) terms\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: terms-termcode\n      path: /terms/{termCode}\n      operations:\n      - name: getterm\n        method: GET\n        description: Get a term by code\n        inputParameters:\n        - name: termCode\n          in: path\n          type: integer\n          required: true\n          description: MedDRA term code (e.g., 10019211 for HLT \"Hepatic failures\")\n        - name: level\n          in: query\n          type: string\n          required: true\n        - name: version\n          in: query\n          type: string\n        - name: language\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hierarchy-level-code-children\n      path: /hierarchy/{level}/{code}/children\n      operations:\n      - name: gettermchildren\n        method: GET\n        description: Get child terms in hierarchy\n     \
  \   inputParameters:\n        - name: level\n          in: path\n          type: string\n          required: true\n          description: Level of the parent term\n        - name: code\n          in: path\n          type: integer\n          required: true\n          description: Code of the parent term\n        - name: version\n          in: query\n          type: string\n        - name: language\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hierarchy-level-code-parents\n      path: /hierarchy/{level}/{code}/parents\n      operations:\n      - name: gettermparents\n        method: GET\n        description: Get parent terms in hierarchy\n        inputParameters:\n        - name: level\n          in: path\n          type: string\n          required: true\n        - name: code\n          in: path\n          type: integer\n          required: true\n   \
  \     - name: version\n          in: query\n          type: string\n        - name: language\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: soc\n      path: /soc\n      operations:\n      - name: listsoc\n        method: GET\n        description: List all System Organ Classes\n        inputParameters:\n        - name: version\n          in: query\n          type: string\n        - name: language\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: validate-code\n      path: /validate/code\n      operations:\n      - name: validatecode\n        method: POST\n        description: Validate a MedDRA code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: versions\n      path: /versions\n      operations:\n      - name: listversions\n        method: GET\n        description: List available MedDRA versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: meddra-rest\n    description: REST adapter for MedDRA Medical Dictionary for Regulatory Activities API.\n    resources:\n    - path: /terms/search\n      name: searchterms\n      operations:\n      - method: GET\n        name: searchterms\n        description: Search MedDRA terms\n        call: meddra.searchterms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /terms/{termCode}\n      name: getterm\n      operations:\n      - method: GET\n        name: getterm\n        description: Get a term by code\n        call: meddra.getterm\n        with:\n          termCode: rest.termCode\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /hierarchy/{level}/{code}/children\n      name: gettermchildren\n      operations:\n      - method: GET\n        name: gettermchildren\n        description: Get child terms in hierarchy\n        call: meddra.gettermchildren\n        with:\n          level: rest.level\n          code: rest.code\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hierarchy/{level}/{code}/parents\n      name: gettermparents\n      operations:\n      - method: GET\n        name: gettermparents\n        description: Get parent terms in hierarchy\n        call: meddra.gettermparents\n        with:\n          level: rest.level\n          code: rest.code\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /soc\n      name: listsoc\n      operations:\n      - method: GET\n        name: listsoc\n        description: List all System Organ Classes\n        call: meddra.listsoc\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /validate/code\n      name: validatecode\n      operations:\n      - method: POST\n        name: validatecode\n        description: Validate a MedDRA code\n        call: meddra.validatecode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /versions\n      name: listversions\n      operations:\n      - method: GET\n        name: listversions\n        description: List available MedDRA versions\n        call: meddra.listversions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: meddra-mcp\n    transport: http\n    description: MCP adapter for MedDRA Medical Dictionary for Regulatory Activities API for AI agent use.\n    tools:\n    - name: searchterms\n      description: Search MedDRA terms\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meddra.searchterms\n\
  \      with:\n        q: tools.q\n        level: tools.level\n        version: tools.version\n        language: tools.language\n        currentOnly: tools.currentOnly\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: q\n        type: string\n        description: Search text (partial match supported)\n        required: true\n      - name: level\n        type: string\n        description: MedDRA hierarchy level to search\n      - name: version\n        type: string\n        description: MedDRA version (e.g., 27.0); defaults to current\n      - name: language\n        type: string\n        description: Language for term text (en, ja, de, fr, es, zh, etc.)\n      - name: currentOnly\n        type: boolean\n        description: Return only current (non-deprecated) terms\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: getterm\n      description: Get a term by code\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meddra.getterm\n      with:\n        termCode: tools.termCode\n        level: tools.level\n        version: tools.version\n        language: tools.language\n      inputParameters:\n      - name: termCode\n        type: integer\n        description: MedDRA term code (e.g., 10019211 for HLT \"Hepatic failures\")\n        required: true\n      - name: level\n        type: string\n        description: level\n        required: true\n      - name: version\n        type: string\n        description: version\n      - name: language\n        type: string\n        description: language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettermchildren\n      description: Get child terms in hierarchy\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: meddra.gettermchildren\n      with:\n        level: tools.level\n        code: tools.code\n        version: tools.version\n        language: tools.language\n      inputParameters:\n      - name: level\n        type: string\n        description: Level of the parent term\n        required: true\n      - name: code\n        type: integer\n        description: Code of the parent term\n        required: true\n      - name: version\n        type: string\n        description: version\n      - name: language\n        type: string\n        description: language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettermparents\n      description: Get parent terms in hierarchy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meddra.gettermparents\n      with:\n        level: tools.level\n        code: tools.code\n        version: tools.version\n        language: tools.language\n\
  \      inputParameters:\n      - name: level\n        type: string\n        description: level\n        required: true\n      - name: code\n        type: integer\n        description: code\n        required: true\n      - name: version\n        type: string\n        description: version\n      - name: language\n        type: string\n        description: language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsoc\n      description: List all System Organ Classes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meddra.listsoc\n      with:\n        version: tools.version\n        language: tools.language\n      inputParameters:\n      - name: version\n        type: string\n        description: version\n      - name: language\n        type: string\n        description: language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validatecode\n      description: Validate\
  \ a MedDRA code\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: meddra.validatecode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listversions\n      description: List available MedDRA versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meddra.listversions\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MEDDRA_TOKEN: MEDDRA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/meddra/refs/heads/main/capabilities/meddra-capability.yaml
tags:
- Meddra
- API
tools:
- description: Search MedDRA terms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchterms
- description: Get a term by code
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getterm
- description: Get child terms in hierarchy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettermchildren
- description: Get parent terms in hierarchy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettermparents
- description: List all System Organ Classes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsoc
- description: Validate a MedDRA code
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: validatecode
- description: List available MedDRA versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listversions
---
