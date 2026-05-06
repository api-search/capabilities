---
categories: []
consumed_apis: []
description: Zally is a quality assurance tool. It's main purpose is to check the complience of API specifications to a specific set of API design rules. The service is able to lint the API specification in OpenAPI format. The result of the linting is a set of Violations. A violation contains information about the violated rule, its severity, and path of the violation in the specification document. The API also provides a result and statistics endpoint. It contains aggregated statics like the number of linting requests and the number of checked endpoints. Additionally, all linting results and the linted AP
layout: capability
name: Zally - Zalando's API Linter
operations:
- description: Zally API Violations
  method: POST
  name: post-api-violations
  path: /api-violations
- description: Zally Get Previous Generated Validation Result
  method: GET
  name: get-api-violations-externalid
  path: /api-violations/{externalId}
- description: Zally Suported Rules
  method: GET
  name: get-supported-rules
  path: /supported-rules
- description: Zally Provides Query Capabilites for Linting Summaries and Automatically Computed Review Statistics.
  method: GET
  name: get-review-statistics
  path: /review-statistics
personas: []
provider_name: Zally
provider_slug: zally
search_terms:
- zally api violations
- api linting
- get api violations externalid
- get supported rules
- zally provides query capabilites for linting summaries and automatically computed review statistics.
- openapi
- api
- api quality
- api design
- zalando
- zally suported rules
- zally
- get review statistics
- post api violations
- open source
- zally get previous generated validation result
slug: zally-capability
source_filename: zally-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Zally - Zalando's API Linter\n  description: Zally is a quality assurance tool. It's main purpose is to check the complience of API specifications to a\n    specific set of API design rules. The service is able to lint the API specification in OpenAPI format. The result of the\n    linting is a set of Violations. A violation contains information about the violated rule, its severity, and path of the\n    violation in the specification document. The API also provides a result and statistics endpoint. It contains aggregated\n    statics like the number of linting requests and the number of checked endpoints. Additionally, all linting results and\n    the linted AP\n  tags:\n  - Zally\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: zally\n    baseUri: https://zally.on.inter.net\n    description: Zally - Zalando's API Linter HTTP API.\n    authentication:\n      type: bearer\n\
  \      token: '{{ZALLY_TOKEN}}'\n    resources:\n    - name: api-violations\n      path: /api-violations\n      operations:\n      - name: post-api-violations\n        method: POST\n        description: Zally API Violations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-violations-externalid\n      path: /api-violations/{externalId}\n      operations:\n      - name: get-api-violations-externalid\n        method: GET\n        description: Zally Get Previous Generated Validation Result\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: supported-rules\n      path: /supported-rules\n      operations:\n      - name: get-supported-rules\n        method: GET\n        description: Zally Suported Rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n    - name: review-statistics\n      path: /review-statistics\n      operations:\n      - name: get-review-statistics\n        method: GET\n        description: Zally Provides Query Capabilites for Linting Summaries and Automatically Computed Review Statistics.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: zally-rest\n    description: REST adapter for Zally - Zalando's API Linter.\n    resources:\n    - path: /api-violations\n      name: post-api-violations\n      operations:\n      - method: POST\n        name: post-api-violations\n        description: Zally API Violations\n        call: zally.post-api-violations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-violations/{externalId}\n      name: get-api-violations-externalid\n      operations:\n      - method: GET\n        name: get-api-violations-externalid\n\
  \        description: Zally Get Previous Generated Validation Result\n        call: zally.get-api-violations-externalid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /supported-rules\n      name: get-supported-rules\n      operations:\n      - method: GET\n        name: get-supported-rules\n        description: Zally Suported Rules\n        call: zally.get-supported-rules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /review-statistics\n      name: get-review-statistics\n      operations:\n      - method: GET\n        name: get-review-statistics\n        description: Zally Provides Query Capabilites for Linting Summaries and Automatically Computed Review Statistics.\n        call: zally.get-review-statistics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: zally-mcp\n    transport: http\n    description: MCP adapter for Zally - Zalando's\
  \ API Linter for AI agent use.\n    tools:\n    - name: post-api-violations\n      description: Zally API Violations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: zally.post-api-violations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-violations-externalid\n      description: Zally Get Previous Generated Validation Result\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zally.get-api-violations-externalid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-supported-rules\n      description: Zally Suported Rules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zally.get-supported-rules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-review-statistics\n      description: Zally Provides Query Capabilites for\
  \ Linting Summaries and Automatically Computed Review Statistics.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: zally.get-review-statistics\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ZALLY_TOKEN: ZALLY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zally/refs/heads/main/capabilities/zally-capability.yaml
tags:
- Zally
- API
tools:
- description: Zally API Violations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-violations
- description: Zally Get Previous Generated Validation Result
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-violations-externalid
- description: Zally Suported Rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-supported-rules
- description: Zally Provides Query Capabilites for Linting Summaries and Automatically Computed Review Statistics.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-review-statistics
---
