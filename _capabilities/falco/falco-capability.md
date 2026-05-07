---
categories: []
consumed_apis: []
description: The Falco HTTP API provides health check, version, and rules management endpoints for the Falco cloud-native runtime security engine. Falco uses eBPF to detect unexpected application behavior and alerts on threats at runtime. This API is served by the Falco web server when enabled via configuration.
layout: capability
name: Falco HTTP API
operations:
- description: Falco Health check
  method: GET
  name: gethealthz
  path: /healthz
- description: Falco Version information
  method: GET
  name: getversion
  path: /version
- description: Falco List loaded rules
  method: GET
  name: getrules
  path: /api/v1/rules
- description: Falco Reload rules
  method: POST
  name: reloadrules
  path: /api/v1/rules/reload
personas: []
provider_name: Falco
provider_slug: falco
search_terms:
- cloud native
- getversion
- reloadrules
- falco version information
- falco health check
- ebpf
- falco list loaded rules
- runtime security
- threat detection
- falco reload rules
- gethealthz
- api
- security
- getrules
- falco
slug: falco-capability
source_filename: falco-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Falco HTTP API\n  description: The Falco HTTP API provides health check, version, and rules management endpoints for the Falco cloud-native\n    runtime security engine. Falco uses eBPF to detect unexpected application behavior and alerts on threats at runtime. This\n    API is served by the Falco web server when enabled via configuration.\n  tags:\n  - Falco\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: falco\n    baseUri: http://localhost:8765\n    description: Falco HTTP API HTTP API.\n    resources:\n    - name: healthz\n      path: /healthz\n      operations:\n      - name: gethealthz\n        method: GET\n        description: Falco Health check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: version\n      path: /version\n      operations:\n      - name: getversion\n \
  \       method: GET\n        description: Falco Version information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-rules\n      path: /api/v1/rules\n      operations:\n      - name: getrules\n        method: GET\n        description: Falco List loaded rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-rules-reload\n      path: /api/v1/rules/reload\n      operations:\n      - name: reloadrules\n        method: POST\n        description: Falco Reload rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: falco-rest\n    description: REST adapter for Falco HTTP API.\n    resources:\n    - path: /healthz\n      name: gethealthz\n      operations:\n      -\
  \ method: GET\n        name: gethealthz\n        description: Falco Health check\n        call: falco.gethealthz\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /version\n      name: getversion\n      operations:\n      - method: GET\n        name: getversion\n        description: Falco Version information\n        call: falco.getversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/rules\n      name: getrules\n      operations:\n      - method: GET\n        name: getrules\n        description: Falco List loaded rules\n        call: falco.getrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/rules/reload\n      name: reloadrules\n      operations:\n      - method: POST\n        name: reloadrules\n        description: Falco Reload rules\n        call: falco.reloadrules\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type:\
  \ mcp\n    port: 9090\n    namespace: falco-mcp\n    transport: http\n    description: MCP adapter for Falco HTTP API for AI agent use.\n    tools:\n    - name: gethealthz\n      description: Falco Health check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: falco.gethealthz\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getversion\n      description: Falco Version information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: falco.getversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrules\n      description: Falco List loaded rules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: falco.getrules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reloadrules\n      description: Falco Reload rules\n      hints:\n     \
  \   readOnly: false\n        destructive: false\n        idempotent: false\n      call: falco.reloadrules\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/falco/refs/heads/main/capabilities/falco-capability.yaml
tags:
- Falco
- API
tools:
- description: Falco Health check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealthz
- description: Falco Version information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getversion
- description: Falco List loaded rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrules
- description: Falco Reload rules
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reloadrules
---
