---
categories: []
consumed_apis: []
description: API providing access to a curated reference library of architecture patterns for distributed systems, microservices, cloud-native applications, and enterprise software.
layout: capability
name: Architecture Pattern API
operations:
- description: List architecture patterns
  method: GET
  name: listpatterns
  path: /patterns
- description: Get architecture pattern details
  method: GET
  name: getpattern
  path: /patterns/{patternId}
- description: Get variants of an architecture pattern
  method: GET
  name: getpatternvariants
  path: /patterns/{patternId}/variants
- description: List pattern domains
  method: GET
  name: listdomains
  path: /domains
- description: List pattern trade-offs
  method: GET
  name: listtradeoffs
  path: /tradeoffs
personas: []
provider_name: Architecture Pattern
provider_slug: architecture-pattern
search_terms:
- pattern
- listpatterns
- listtradeoffs
- listdomains
- get variants of an architecture pattern
- getpatternvariants
- cloud native
- design patterns
- getpattern
- architecture
- api
- architecture patterns
- list pattern trade-offs
- system design
- list pattern domains
- list architecture patterns
- get architecture pattern details
- microservices
- software architecture
slug: architecture-pattern-capability
source_filename: architecture-pattern-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Architecture Pattern API\n  description: API providing access to a curated reference library of architecture patterns for distributed systems, microservices,\n    cloud-native applications, and enterprise software.\n  tags:\n  - Architecture\n  - Pattern\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: architecture-pattern\n    baseUri: https://api.apievangelist.com/v1/architecture-patterns\n    description: Architecture Pattern API HTTP API.\n    resources:\n    - name: patterns\n      path: /patterns\n      operations:\n      - name: listpatterns\n        method: GET\n        description: List architecture patterns\n        inputParameters:\n        - name: domain\n          in: query\n          type: string\n          description: Filter by pattern domain\n        - name: tag\n          in: query\n          type: string\n        - name: limit\n          in: query\n\
  \          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patterns-patternid\n      path: /patterns/{patternId}\n      operations:\n      - name: getpattern\n        method: GET\n        description: Get architecture pattern details\n        inputParameters:\n        - name: patternId\n          in: path\n          type: string\n          required: true\n          description: The unique pattern identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patterns-patternid-variants\n      path: /patterns/{patternId}/variants\n      operations:\n      - name: getpatternvariants\n        method: GET\n        description: Get variants of an architecture pattern\n        inputParameters:\n        - name: patternId\n          in:\
  \ path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains\n      path: /domains\n      operations:\n      - name: listdomains\n        method: GET\n        description: List pattern domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tradeoffs\n      path: /tradeoffs\n      operations:\n      - name: listtradeoffs\n        method: GET\n        description: List pattern trade-offs\n        inputParameters:\n        - name: patternId\n          in: query\n          type: string\n          description: Filter trade-offs by pattern\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: architecture-pattern-rest\n    description:\
  \ REST adapter for Architecture Pattern API.\n    resources:\n    - path: /patterns\n      name: listpatterns\n      operations:\n      - method: GET\n        name: listpatterns\n        description: List architecture patterns\n        call: architecture-pattern.listpatterns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patterns/{patternId}\n      name: getpattern\n      operations:\n      - method: GET\n        name: getpattern\n        description: Get architecture pattern details\n        call: architecture-pattern.getpattern\n        with:\n          patternId: rest.patternId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patterns/{patternId}/variants\n      name: getpatternvariants\n      operations:\n      - method: GET\n        name: getpatternvariants\n        description: Get variants of an architecture pattern\n        call: architecture-pattern.getpatternvariants\n        with:\n          patternId:\
  \ rest.patternId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /domains\n      name: listdomains\n      operations:\n      - method: GET\n        name: listdomains\n        description: List pattern domains\n        call: architecture-pattern.listdomains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tradeoffs\n      name: listtradeoffs\n      operations:\n      - method: GET\n        name: listtradeoffs\n        description: List pattern trade-offs\n        call: architecture-pattern.listtradeoffs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: architecture-pattern-mcp\n    transport: http\n    description: MCP adapter for Architecture Pattern API for AI agent use.\n    tools:\n    - name: listpatterns\n      description: List architecture patterns\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: architecture-pattern.listpatterns\n      with:\n        domain: tools.domain\n        tag: tools.tag\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: domain\n        type: string\n        description: Filter by pattern domain\n      - name: tag\n        type: string\n        description: tag\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpattern\n      description: Get architecture pattern details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architecture-pattern.getpattern\n      with:\n        patternId: tools.patternId\n      inputParameters:\n      - name: patternId\n        type: string\n        description: The unique pattern identifier\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getpatternvariants\n      description: Get variants of an architecture pattern\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architecture-pattern.getpatternvariants\n      with:\n        patternId: tools.patternId\n      inputParameters:\n      - name: patternId\n        type: string\n        description: patternId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdomains\n      description: List pattern domains\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architecture-pattern.listdomains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtradeoffs\n      description: List pattern trade-offs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: architecture-pattern.listtradeoffs\n\
  \      with:\n        patternId: tools.patternId\n      inputParameters:\n      - name: patternId\n        type: string\n        description: Filter trade-offs by pattern\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/architecture-pattern/refs/heads/main/capabilities/architecture-pattern-capability.yaml
tags:
- Architecture
- Pattern
- API
tools:
- description: List architecture patterns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpatterns
- description: Get architecture pattern details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpattern
- description: Get variants of an architecture pattern
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpatternvariants
- description: List pattern domains
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdomains
- description: List pattern trade-offs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtradeoffs
---
