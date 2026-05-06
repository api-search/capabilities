---
categories: []
consumed_apis: []
description: API providing access to a catalog of architectural design patterns, their descriptions, use cases, implementation examples, and relationships between patterns.
layout: capability
name: Architectural Design Patterns API
operations:
- description: List architectural design patterns
  method: GET
  name: listpatterns
  path: /patterns
- description: Get design pattern details
  method: GET
  name: getpattern
  path: /patterns/{patternId}
- description: Get implementation examples for a pattern
  method: GET
  name: getpatternexamples
  path: /patterns/{patternId}/examples
- description: Get relationships for a pattern
  method: GET
  name: getpatternrelationships
  path: /patterns/{patternId}/relationships
- description: List pattern categories
  method: GET
  name: listcategories
  path: /categories
- description: List anti-patterns
  method: GET
  name: listantipatterns
  path: /anti-patterns
personas: []
provider_name: Architectural Design Patterns
provider_slug: architectural-design-patterns
search_terms:
- listpatterns
- best practices
- get implementation examples for a pattern
- list pattern categories
- design
- patterns
- list anti-patterns
- listcategories
- architectural
- design patterns
- list architectural design patterns
- get relationships for a pattern
- getpattern
- get design pattern details
- api
- getpatternexamples
- system design
- software engineering
- getpatternrelationships
- microservices
- listantipatterns
- software architecture
slug: architectural-design-patterns-capability
source_filename: architectural-design-patterns-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Architectural Design Patterns API\n  description: API providing access to a catalog of architectural design patterns, their descriptions, use cases, implementation\n    examples, and relationships between patterns.\n  tags:\n  - Architectural\n  - Design\n  - Patterns\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: architectural-design-patterns\n    baseUri: https://api.apievangelist.com/v1/architectural-design-patterns\n    description: Architectural Design Patterns API HTTP API.\n    resources:\n    - name: patterns\n      path: /patterns\n      operations:\n      - name: listpatterns\n        method: GET\n        description: List architectural design patterns\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          description: Filter by pattern category\n        - name: tag\n          in: query\n          type:\
  \ string\n          description: Filter by tag\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patterns-patternid\n      path: /patterns/{patternId}\n      operations:\n      - name: getpattern\n        method: GET\n        description: Get design pattern details\n        inputParameters:\n        - name: patternId\n          in: path\n          type: string\n          required: true\n          description: The unique pattern identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patterns-patternid-examples\n      path: /patterns/{patternId}/examples\n      operations:\n      - name: getpatternexamples\n        method: GET\n        description: Get implementation examples\
  \ for a pattern\n        inputParameters:\n        - name: patternId\n          in: path\n          type: string\n          required: true\n        - name: language\n          in: query\n          type: string\n          description: Programming language for examples\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patterns-patternid-relationships\n      path: /patterns/{patternId}/relationships\n      operations:\n      - name: getpatternrelationships\n        method: GET\n        description: Get relationships for a pattern\n        inputParameters:\n        - name: patternId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /categories\n      operations:\n      - name: listcategories\n        method: GET\n      \
  \  description: List pattern categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: anti-patterns\n      path: /anti-patterns\n      operations:\n      - name: listantipatterns\n        method: GET\n        description: List anti-patterns\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: architectural-design-patterns-rest\n    description: REST adapter for Architectural Design Patterns API.\n    resources:\n    - path: /patterns\n      name: listpatterns\n      operations:\n      - method: GET\n        name: listpatterns\n        description: List architectural design patterns\n        call: architectural-design-patterns.listpatterns\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patterns/{patternId}\n      name: getpattern\n      operations:\n      - method: GET\n        name: getpattern\n        description: Get design pattern details\n        call: architectural-design-patterns.getpattern\n        with:\n          patternId: rest.patternId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patterns/{patternId}/examples\n      name: getpatternexamples\n      operations:\n      - method: GET\n        name: getpatternexamples\n        description: Get implementation examples for a pattern\n        call: architectural-design-patterns.getpatternexamples\n        with:\n          patternId: rest.patternId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patterns/{patternId}/relationships\n      name: getpatternrelationships\n      operations:\n      - method: GET\n        name: getpatternrelationships\n\
  \        description: Get relationships for a pattern\n        call: architectural-design-patterns.getpatternrelationships\n        with:\n          patternId: rest.patternId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /categories\n      name: listcategories\n      operations:\n      - method: GET\n        name: listcategories\n        description: List pattern categories\n        call: architectural-design-patterns.listcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /anti-patterns\n      name: listantipatterns\n      operations:\n      - method: GET\n        name: listantipatterns\n        description: List anti-patterns\n        call: architectural-design-patterns.listantipatterns\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: architectural-design-patterns-mcp\n    transport: http\n    description: MCP adapter for Architectural\
  \ Design Patterns API for AI agent use.\n    tools:\n    - name: listpatterns\n      description: List architectural design patterns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architectural-design-patterns.listpatterns\n      with:\n        category: tools.category\n        tag: tools.tag\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: category\n        type: string\n        description: Filter by pattern category\n      - name: tag\n        type: string\n        description: Filter by tag\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpattern\n      description: Get design pattern details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architectural-design-patterns.getpattern\n\
  \      with:\n        patternId: tools.patternId\n      inputParameters:\n      - name: patternId\n        type: string\n        description: The unique pattern identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatternexamples\n      description: Get implementation examples for a pattern\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architectural-design-patterns.getpatternexamples\n      with:\n        patternId: tools.patternId\n        language: tools.language\n      inputParameters:\n      - name: patternId\n        type: string\n        description: patternId\n        required: true\n      - name: language\n        type: string\n        description: Programming language for examples\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpatternrelationships\n      description: Get relationships for a pattern\n      hints:\n   \
  \     readOnly: true\n        destructive: false\n        idempotent: true\n      call: architectural-design-patterns.getpatternrelationships\n      with:\n        patternId: tools.patternId\n      inputParameters:\n      - name: patternId\n        type: string\n        description: patternId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcategories\n      description: List pattern categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architectural-design-patterns.listcategories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listantipatterns\n      description: List anti-patterns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architectural-design-patterns.listantipatterns\n      with:\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      -\
  \ name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/architectural-design-patterns/refs/heads/main/capabilities/architectural-design-patterns-capability.yaml
tags:
- Architectural
- Design
- Patterns
- API
tools:
- description: List architectural design patterns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpatterns
- description: Get design pattern details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpattern
- description: Get implementation examples for a pattern
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatternexamples
- description: Get relationships for a pattern
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatternrelationships
- description: List pattern categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcategories
- description: List anti-patterns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listantipatterns
---
