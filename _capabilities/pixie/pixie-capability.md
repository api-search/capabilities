---
categories: []
consumed_apis: []
description: The Pixie API provides programmatic access to the Pixie Kubernetes observability platform. It enables listing and managing clusters, executing PxL scripts to query telemetry data collected via eBPF, and retrieving results including full-body application requests, resource metrics, and network data without requiring manual instrumentation.
layout: capability
name: Pixie API
operations:
- description: Pixie List clusters
  method: GET
  name: listclusters
  path: /api/clusters
- description: Pixie Get cluster details
  method: GET
  name: getcluster
  path: /api/clusters/{cluster_id}
- description: Pixie Execute a PxL script
  method: POST
  name: executescript
  path: /api/pxl/execute
- description: Pixie Health check
  method: GET
  name: gethealth
  path: /api/health
personas: []
provider_name: Pixie
provider_slug: pixie
search_terms:
- observability
- monitoring
- pixie execute a pxl script
- ebpf
- pixie health check
- pixie list clusters
- getcluster
- executescript
- gethealth
- listclusters
- api
- pixie
- pixie get cluster details
- kubernetes
slug: pixie-capability
source_filename: pixie-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pixie API\n  description: The Pixie API provides programmatic access to the Pixie Kubernetes observability platform. It enables listing\n    and managing clusters, executing PxL scripts to query telemetry data collected via eBPF, and retrieving results including\n    full-body application requests, resource metrics, and network data without requiring manual instrumentation.\n  tags:\n  - Pixie\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pixie\n    baseUri: https://work.withpixie.ai\n    description: Pixie API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: pixie-api-key\n      value: '{{PIXIE_TOKEN}}'\n    resources:\n    - name: api-clusters\n      path: /api/clusters\n      operations:\n      - name: listclusters\n        method: GET\n        description: Pixie List clusters\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-clusters-cluster-id\n      path: /api/clusters/{cluster_id}\n      operations:\n      - name: getcluster\n        method: GET\n        description: Pixie Get cluster details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-pxl-execute\n      path: /api/pxl/execute\n      operations:\n      - name: executescript\n        method: POST\n        description: Pixie Execute a PxL script\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-health\n      path: /api/health\n      operations:\n      - name: gethealth\n        method: GET\n        description: Pixie Health check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n\
  \    port: 8080\n    namespace: pixie-rest\n    description: REST adapter for Pixie API.\n    resources:\n    - path: /api/clusters\n      name: listclusters\n      operations:\n      - method: GET\n        name: listclusters\n        description: Pixie List clusters\n        call: pixie.listclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/clusters/{cluster_id}\n      name: getcluster\n      operations:\n      - method: GET\n        name: getcluster\n        description: Pixie Get cluster details\n        call: pixie.getcluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/pxl/execute\n      name: executescript\n      operations:\n      - method: POST\n        name: executescript\n        description: Pixie Execute a PxL script\n        call: pixie.executescript\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/health\n      name: gethealth\n     \
  \ operations:\n      - method: GET\n        name: gethealth\n        description: Pixie Health check\n        call: pixie.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pixie-mcp\n    transport: http\n    description: MCP adapter for Pixie API for AI agent use.\n    tools:\n    - name: listclusters\n      description: Pixie List clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pixie.listclusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcluster\n      description: Pixie Get cluster details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pixie.getcluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executescript\n      description: Pixie Execute a PxL script\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: pixie.executescript\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethealth\n      description: Pixie Health check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pixie.gethealth\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PIXIE_TOKEN: PIXIE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pixie/refs/heads/main/capabilities/pixie-capability.yaml
tags:
- Pixie
- API
tools:
- description: Pixie List clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusters
- description: Pixie Get cluster details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcluster
- description: Pixie Execute a PxL script
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executescript
- description: Pixie Health check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
---
