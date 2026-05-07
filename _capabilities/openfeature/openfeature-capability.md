---
categories: []
consumed_apis: []
description: '--- The **OpenFeature Remote Evaluation Protocol (OFREP)** is an API specification for feature flagging that enables vendor-agnostic communication between applications and flag management systems. OFREP defines a standard API layer between OpenFeature providers and flag management systems, allowing any flag management system to implement the protocol and be compatible with community-maintained providers. For more information, see the [OFREP documentation](https://openfeature.dev/docs/reference/other-technologies/ofrep/).'
layout: capability
name: OpenFeature Remote Evaluation Protocol (OFREP)
operations:
- description: Evaluate A Single Feature Flag
  method: POST
  name: evaluateflag
  path: /ofrep/v1/evaluate/flags/{key}
- description: Bulk Evaluate All Feature Flags
  method: POST
  name: evaluateflagsbulk
  path: /ofrep/v1/evaluate/flags
personas: []
provider_name: OpenFeature
provider_slug: openfeature
search_terms:
- cloud native
- incubating
- feature management
- evaluateflag
- feature flags
- specification
- openfeature
- evaluateflagsbulk
- bulk evaluate all feature flags
- sdks
- api
- evaluate a single feature flag
slug: openfeature-capability
source_filename: openfeature-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenFeature Remote Evaluation Protocol (OFREP)\n  description: '--- The **OpenFeature Remote Evaluation Protocol (OFREP)** is an API specification for feature flagging that\n    enables vendor-agnostic communication between applications and flag management systems. OFREP defines a standard API layer\n    between OpenFeature providers and flag management systems, allowing any flag management system to implement the protocol\n    and be compatible with community-maintained providers. For more information, see the [OFREP documentation](https://openfeature.dev/docs/reference/other-technologies/ofrep/).'\n  tags:\n  - Openfeature\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openfeature\n    baseUri: ''\n    description: OpenFeature Remote Evaluation Protocol (OFREP) HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OPENFEATURE_TOKEN}}'\n    resources:\n\
  \    - name: ofrep-v1-evaluate-flags-key\n      path: /ofrep/v1/evaluate/flags/{key}\n      operations:\n      - name: evaluateflag\n        method: POST\n        description: Evaluate A Single Feature Flag\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: The unique identifier (key) of the feature flag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ofrep-v1-evaluate-flags\n      path: /ofrep/v1/evaluate/flags\n      operations:\n      - name: evaluateflagsbulk\n        method: POST\n        description: Bulk Evaluate All Feature Flags\n        inputParameters:\n        - name: If-None-Match\n          in: header\n          type: string\n          description: Optional ETag value from a previous bulk evaluation response. If provided and the ETag matches the\n            current flag set, the server will return\
  \ a 304 Not Modified r\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openfeature-rest\n    description: REST adapter for OpenFeature Remote Evaluation Protocol (OFREP).\n    resources:\n    - path: /ofrep/v1/evaluate/flags/{key}\n      name: evaluateflag\n      operations:\n      - method: POST\n        name: evaluateflag\n        description: Evaluate A Single Feature Flag\n        call: openfeature.evaluateflag\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ofrep/v1/evaluate/flags\n      name: evaluateflagsbulk\n      operations:\n      - method: POST\n        name: evaluateflagsbulk\n        description: Bulk Evaluate All Feature Flags\n        call: openfeature.evaluateflagsbulk\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9090\n    namespace: openfeature-mcp\n    transport: http\n    description: MCP adapter for OpenFeature Remote Evaluation Protocol (OFREP) for AI agent use.\n    tools:\n    - name: evaluateflag\n      description: Evaluate A Single Feature Flag\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openfeature.evaluateflag\n      with:\n        key: tools.key\n      inputParameters:\n      - name: key\n        type: string\n        description: The unique identifier (key) of the feature flag\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: evaluateflagsbulk\n      description: Bulk Evaluate All Feature Flags\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: openfeature.evaluateflagsbulk\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPENFEATURE_TOKEN:\
  \ OPENFEATURE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openfeature/refs/heads/main/capabilities/openfeature-capability.yaml
tags:
- Openfeature
- API
tools:
- description: Evaluate A Single Feature Flag
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: evaluateflag
- description: Bulk Evaluate All Feature Flags
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: evaluateflagsbulk
---
