---
categories: []
consumed_apis: []
description: The Linkerd proxy exposes an admin HTTP server on each meshed pod, providing health check endpoints, readiness probes, Prometheus-compatible metrics, and runtime diagnostic information. By default this server listens on port 4191.
layout: capability
name: Linkerd Proxy Admin API
operations:
- description: Linkerd Get proxy metrics
  method: GET
  name: getproxymetrics
  path: /metrics
- description: Linkerd Proxy readiness check
  method: GET
  name: getproxyreadiness
  path: /ready
- description: Linkerd Proxy liveness check
  method: GET
  name: getproxyliveness
  path: /live
- description: Linkerd Initiate proxy shutdown
  method: POST
  name: shutdownproxy
  path: /shutdown
personas: []
provider_name: Linkerd
provider_slug: linkerd
search_terms:
- linkerd proxy liveness check
- observability
- linkerd
- service mesh
- shutdownproxy
- getproxyreadiness
- mtls
- getproxymetrics
- getproxyliveness
- security
- api
- linkerd proxy readiness check
- linkerd get proxy metrics
- linkerd initiate proxy shutdown
- kubernetes
slug: linkerd-capability
source_filename: linkerd-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Linkerd Proxy Admin API\n  description: The Linkerd proxy exposes an admin HTTP server on each meshed pod, providing health check endpoints, readiness\n    probes, Prometheus-compatible metrics, and runtime diagnostic information. By default this server listens on port 4191.\n  tags:\n  - Linkerd\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: linkerd\n    baseUri: http://localhost:4191\n    description: Linkerd Proxy Admin API HTTP API.\n    resources:\n    - name: metrics\n      path: /metrics\n      operations:\n      - name: getproxymetrics\n        method: GET\n        description: Linkerd Get proxy metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ready\n      path: /ready\n      operations:\n      - name: getproxyreadiness\n        method: GET\n        description:\
  \ Linkerd Proxy readiness check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live\n      path: /live\n      operations:\n      - name: getproxyliveness\n        method: GET\n        description: Linkerd Proxy liveness check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shutdown\n      path: /shutdown\n      operations:\n      - name: shutdownproxy\n        method: POST\n        description: Linkerd Initiate proxy shutdown\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: linkerd-rest\n    description: REST adapter for Linkerd Proxy Admin API.\n    resources:\n    - path: /metrics\n      name: getproxymetrics\n      operations:\n      - method: GET\n        name: getproxymetrics\n\
  \        description: Linkerd Get proxy metrics\n        call: linkerd.getproxymetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ready\n      name: getproxyreadiness\n      operations:\n      - method: GET\n        name: getproxyreadiness\n        description: Linkerd Proxy readiness check\n        call: linkerd.getproxyreadiness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /live\n      name: getproxyliveness\n      operations:\n      - method: GET\n        name: getproxyliveness\n        description: Linkerd Proxy liveness check\n        call: linkerd.getproxyliveness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shutdown\n      name: shutdownproxy\n      operations:\n      - method: POST\n        name: shutdownproxy\n        description: Linkerd Initiate proxy shutdown\n        call: linkerd.shutdownproxy\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: linkerd-mcp\n    transport: http\n    description: MCP adapter for Linkerd Proxy Admin API for AI agent use.\n    tools:\n    - name: getproxymetrics\n      description: Linkerd Get proxy metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: linkerd.getproxymetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproxyreadiness\n      description: Linkerd Proxy readiness check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: linkerd.getproxyreadiness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproxyliveness\n      description: Linkerd Proxy liveness check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: linkerd.getproxyliveness\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: shutdownproxy\n      description: Linkerd Initiate proxy shutdown\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: linkerd.shutdownproxy\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linkerd/refs/heads/main/capabilities/linkerd-capability.yaml
tags:
- Linkerd
- API
tools:
- description: Linkerd Get proxy metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproxymetrics
- description: Linkerd Proxy readiness check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproxyreadiness
- description: Linkerd Proxy liveness check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproxyliveness
- description: Linkerd Initiate proxy shutdown
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: shutdownproxy
---
