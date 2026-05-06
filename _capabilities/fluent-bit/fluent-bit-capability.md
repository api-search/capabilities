---
categories: []
consumed_apis: []
description: Fluent Bit exposes an embedded HTTP server for runtime monitoring, internal metrics, storage statistics, health checks, and hot reloading. Endpoints are available under v1 (legacy) and v2 (current) paths and respond in JSON, Prometheus 0.0.4, or cmetrics text format.
layout: capability
name: Fluent Bit Monitoring HTTP API
operations:
- description: Build information
  method: GET
  name: get
  path: /
- description: Uptime information
  method: GET
  name: get-api-v1-uptime
  path: /api/v1/uptime
- description: Internal metrics (v1, JSON)
  method: GET
  name: get-api-v1-metrics
  path: /api/v1/metrics
- description: Internal metrics (v1, Prometheus)
  method: GET
  name: get-api-v1-metrics-prometheus
  path: /api/v1/metrics/prometheus
- description: Storage layer metrics
  method: GET
  name: get-api-v1-storage
  path: /api/v1/storage
- description: Health check (v1)
  method: GET
  name: get-api-v1-health
  path: /api/v1/health
- description: Internal metrics (v2, cmetrics)
  method: GET
  name: get-api-v2-metrics
  path: /api/v2/metrics
- description: Internal metrics (v2, Prometheus)
  method: GET
  name: get-api-v2-metrics-prometheus
  path: /api/v2/metrics/prometheus
- description: Health status (v2, JSON)
  method: GET
  name: get-api-v2-health
  path: /api/v2/health
- description: Get hot reload status
  method: GET
  name: get-api-v2-reload
  path: /api/v2/reload
- description: Trigger hot reload
  method: POST
  name: post-api-v2-reload
  path: /api/v2/reload
- description: Trigger hot reload (PUT)
  method: PUT
  name: put-api-v2-reload
  path: /api/v2/reload
personas: []
provider_name: Fluent Bit
provider_slug: fluent-bit
search_terms:
- get api v2 reload
- post api v2 reload
- internal metrics (v2, prometheus)
- build information
- internal metrics (v1, json)
- metrics
- get
- get api v1 health
- storage layer metrics
- get api v2 health
- internal metrics (v1, prometheus)
- open source
- get api v1 metrics
- internal metrics (v2, cmetrics)
- get hot reload status
- api
- observability
- bit
- health status (v2, json)
- get api v2 metrics
- get api v1 metrics prometheus
- put api v2 reload
- trigger hot reload (put)
- fluent
- get api v1 storage
- uptime information
- health check (v1)
- get api v2 metrics prometheus
- trigger hot reload
- logging
- get api v1 uptime
slug: fluent-bit-capability
source_filename: fluent-bit-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fluent Bit Monitoring HTTP API\n  description: Fluent Bit exposes an embedded HTTP server for runtime monitoring, internal metrics, storage statistics, health\n    checks, and hot reloading. Endpoints are available under v1 (legacy) and v2 (current) paths and respond in JSON, Prometheus\n    0.0.4, or cmetrics text format.\n  tags:\n  - Fluent\n  - Bit\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fluent-bit\n    baseUri: http://127.0.0.1:2020\n    description: Fluent Bit Monitoring HTTP API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: get\n        method: GET\n        description: Build information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-uptime\n      path: /api/v1/uptime\n      operations:\n      - name: get-api-v1-uptime\n\
  \        method: GET\n        description: Uptime information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-metrics\n      path: /api/v1/metrics\n      operations:\n      - name: get-api-v1-metrics\n        method: GET\n        description: Internal metrics (v1, JSON)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-metrics-prometheus\n      path: /api/v1/metrics/prometheus\n      operations:\n      - name: get-api-v1-metrics-prometheus\n        method: GET\n        description: Internal metrics (v1, Prometheus)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-storage\n      path: /api/v1/storage\n      operations:\n      - name: get-api-v1-storage\n        method: GET\n        description: Storage\
  \ layer metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-health\n      path: /api/v1/health\n      operations:\n      - name: get-api-v1-health\n        method: GET\n        description: Health check (v1)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-metrics\n      path: /api/v2/metrics\n      operations:\n      - name: get-api-v2-metrics\n        method: GET\n        description: Internal metrics (v2, cmetrics)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-metrics-prometheus\n      path: /api/v2/metrics/prometheus\n      operations:\n      - name: get-api-v2-metrics-prometheus\n        method: GET\n        description: Internal metrics (v2, Prometheus)\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-health\n      path: /api/v2/health\n      operations:\n      - name: get-api-v2-health\n        method: GET\n        description: Health status (v2, JSON)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-reload\n      path: /api/v2/reload\n      operations:\n      - name: get-api-v2-reload\n        method: GET\n        description: Get hot reload status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-v2-reload\n        method: POST\n        description: Trigger hot reload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-api-v2-reload\n        method: PUT\n        description: Trigger\
  \ hot reload (PUT)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fluent-bit-rest\n    description: REST adapter for Fluent Bit Monitoring HTTP API.\n    resources:\n    - path: /\n      name: get\n      operations:\n      - method: GET\n        name: get\n        description: Build information\n        call: fluent-bit.get\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/uptime\n      name: get-api-v1-uptime\n      operations:\n      - method: GET\n        name: get-api-v1-uptime\n        description: Uptime information\n        call: fluent-bit.get-api-v1-uptime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/metrics\n      name: get-api-v1-metrics\n      operations:\n      - method: GET\n        name: get-api-v1-metrics\n        description: Internal metrics\
  \ (v1, JSON)\n        call: fluent-bit.get-api-v1-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/metrics/prometheus\n      name: get-api-v1-metrics-prometheus\n      operations:\n      - method: GET\n        name: get-api-v1-metrics-prometheus\n        description: Internal metrics (v1, Prometheus)\n        call: fluent-bit.get-api-v1-metrics-prometheus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/storage\n      name: get-api-v1-storage\n      operations:\n      - method: GET\n        name: get-api-v1-storage\n        description: Storage layer metrics\n        call: fluent-bit.get-api-v1-storage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/health\n      name: get-api-v1-health\n      operations:\n      - method: GET\n        name: get-api-v1-health\n        description: Health check (v1)\n        call: fluent-bit.get-api-v1-health\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/metrics\n      name: get-api-v2-metrics\n      operations:\n      - method: GET\n        name: get-api-v2-metrics\n        description: Internal metrics (v2, cmetrics)\n        call: fluent-bit.get-api-v2-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/metrics/prometheus\n      name: get-api-v2-metrics-prometheus\n      operations:\n      - method: GET\n        name: get-api-v2-metrics-prometheus\n        description: Internal metrics (v2, Prometheus)\n        call: fluent-bit.get-api-v2-metrics-prometheus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/health\n      name: get-api-v2-health\n      operations:\n      - method: GET\n        name: get-api-v2-health\n        description: Health status (v2, JSON)\n        call: fluent-bit.get-api-v2-health\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /api/v2/reload\n      name: get-api-v2-reload\n      operations:\n      - method: GET\n        name: get-api-v2-reload\n        description: Get hot reload status\n        call: fluent-bit.get-api-v2-reload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/reload\n      name: post-api-v2-reload\n      operations:\n      - method: POST\n        name: post-api-v2-reload\n        description: Trigger hot reload\n        call: fluent-bit.post-api-v2-reload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/reload\n      name: put-api-v2-reload\n      operations:\n      - method: PUT\n        name: put-api-v2-reload\n        description: Trigger hot reload (PUT)\n        call: fluent-bit.put-api-v2-reload\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fluent-bit-mcp\n    transport: http\n\
  \    description: MCP adapter for Fluent Bit Monitoring HTTP API for AI agent use.\n    tools:\n    - name: get\n      description: Build information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fluent-bit.get\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-v1-uptime\n      description: Uptime information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fluent-bit.get-api-v1-uptime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-v1-metrics\n      description: Internal metrics (v1, JSON)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fluent-bit.get-api-v1-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-v1-metrics-prometheus\n      description: Internal metrics (v1, Prometheus)\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fluent-bit.get-api-v1-metrics-prometheus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-v1-storage\n      description: Storage layer metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fluent-bit.get-api-v1-storage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-v1-health\n      description: Health check (v1)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fluent-bit.get-api-v1-health\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-v2-metrics\n      description: Internal metrics (v2, cmetrics)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fluent-bit.get-api-v2-metrics\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: get-api-v2-metrics-prometheus\n      description: Internal metrics (v2, Prometheus)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fluent-bit.get-api-v2-metrics-prometheus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-v2-health\n      description: Health status (v2, JSON)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fluent-bit.get-api-v2-health\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-v2-reload\n      description: Get hot reload status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fluent-bit.get-api-v2-reload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-api-v2-reload\n      description: Trigger hot reload\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: fluent-bit.post-api-v2-reload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-api-v2-reload\n      description: Trigger hot reload (PUT)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: fluent-bit.put-api-v2-reload\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fluent-bit/refs/heads/main/capabilities/fluent-bit-capability.yaml
tags:
- Fluent
- Bit
- API
tools:
- description: Build information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Uptime information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v1-uptime
- description: Internal metrics (v1, JSON)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v1-metrics
- description: Internal metrics (v1, Prometheus)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v1-metrics-prometheus
- description: Storage layer metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v1-storage
- description: Health check (v1)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v1-health
- description: Internal metrics (v2, cmetrics)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v2-metrics
- description: Internal metrics (v2, Prometheus)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v2-metrics-prometheus
- description: Health status (v2, JSON)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v2-health
- description: Get hot reload status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-v2-reload
- description: Trigger hot reload
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-v2-reload
- description: Trigger hot reload (PUT)
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-v2-reload
---
