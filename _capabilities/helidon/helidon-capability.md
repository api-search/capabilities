---
categories: []
consumed_apis: []
description: Helidon provides built-in observability endpoints following the MicroProfile Health and MicroProfile Metrics specifications. These endpoints expose application health status, readiness, liveness, startup checks, and application/vendor/base metrics. In Helidon 4.x, these are served under the /observe path by default.
layout: capability
name: Helidon Observe (Health & Metrics) API
operations:
- description: Helidon Overall health status
  method: GET
  name: gethealth
  path: /observe/health
- description: Helidon Liveness check
  method: GET
  name: getliveness
  path: /observe/health/live
- description: Helidon Readiness check
  method: GET
  name: getreadiness
  path: /observe/health/ready
- description: Helidon Startup check
  method: GET
  name: getstartup
  path: /observe/health/started
- description: Helidon All metrics
  method: GET
  name: getmetrics
  path: /observe/metrics
- description: Helidon Application metrics
  method: GET
  name: getapplicationmetrics
  path: /observe/metrics/application
- description: Helidon Vendor metrics
  method: GET
  name: getvendormetrics
  path: /observe/metrics/vendor
- description: Helidon Base metrics
  method: GET
  name: getbasemetrics
  path: /observe/metrics/base
- description: Helidon Application info
  method: GET
  name: getinfo
  path: /observe/info
- description: Helidon OpenAPI document
  method: GET
  name: getopenapi
  path: /openapi
personas: []
provider_name: Helidon
provider_slug: helidon
search_terms:
- helidon application metrics
- helidon openapi document
- helidon application info
- helidon startup check
- helidon vendor metrics
- getmetrics
- getvendormetrics
- helidon all metrics
- getapplicationmetrics
- java
- helidon base metrics
- getinfo
- helidon overall health status
- cloud native
- gethealth
- oracle
- getbasemetrics
- api
- helidon readiness check
- getliveness
- helidon
- helidon liveness check
- getstartup
- getreadiness
- frameworks
- reactive
- microservices
- getopenapi
- microprofile
slug: helidon-capability
source_filename: helidon-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Helidon Observe (Health & Metrics) API\n  description: Helidon provides built-in observability endpoints following the MicroProfile Health and MicroProfile Metrics\n    specifications. These endpoints expose application health status, readiness, liveness, startup checks, and application/vendor/base\n    metrics. In Helidon 4.x, these are served under the /observe path by default.\n  tags:\n  - Helidon\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: helidon\n    baseUri: http://localhost:8080\n    description: Helidon Observe (Health & Metrics) API HTTP API.\n    resources:\n    - name: observe-health\n      path: /observe/health\n      operations:\n      - name: gethealth\n        method: GET\n        description: Helidon Overall health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: observe-health-live\n      path: /observe/health/live\n      operations:\n      - name: getliveness\n        method: GET\n        description: Helidon Liveness check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observe-health-ready\n      path: /observe/health/ready\n      operations:\n      - name: getreadiness\n        method: GET\n        description: Helidon Readiness check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observe-health-started\n      path: /observe/health/started\n      operations:\n      - name: getstartup\n        method: GET\n        description: Helidon Startup check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observe-metrics\n      path: /observe/metrics\n      operations:\n\
  \      - name: getmetrics\n        method: GET\n        description: Helidon All metrics\n        inputParameters:\n        - name: Accept\n          in: header\n          type: string\n          description: Response format (text/plain for Prometheus, application/json for JSON)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observe-metrics-application\n      path: /observe/metrics/application\n      operations:\n      - name: getapplicationmetrics\n        method: GET\n        description: Helidon Application metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observe-metrics-vendor\n      path: /observe/metrics/vendor\n      operations:\n      - name: getvendormetrics\n        method: GET\n        description: Helidon Vendor metrics\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: observe-metrics-base\n      path: /observe/metrics/base\n      operations:\n      - name: getbasemetrics\n        method: GET\n        description: Helidon Base metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: observe-info\n      path: /observe/info\n      operations:\n      - name: getinfo\n        method: GET\n        description: Helidon Application info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: openapi\n      path: /openapi\n      operations:\n      - name: getopenapi\n        method: GET\n        description: Helidon OpenAPI document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ helidon-rest\n    description: REST adapter for Helidon Observe (Health & Metrics) API.\n    resources:\n    - path: /observe/health\n      name: gethealth\n      operations:\n      - method: GET\n        name: gethealth\n        description: Helidon Overall health status\n        call: helidon.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /observe/health/live\n      name: getliveness\n      operations:\n      - method: GET\n        name: getliveness\n        description: Helidon Liveness check\n        call: helidon.getliveness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /observe/health/ready\n      name: getreadiness\n      operations:\n      - method: GET\n        name: getreadiness\n        description: Helidon Readiness check\n        call: helidon.getreadiness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /observe/health/started\n      name: getstartup\n\
  \      operations:\n      - method: GET\n        name: getstartup\n        description: Helidon Startup check\n        call: helidon.getstartup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /observe/metrics\n      name: getmetrics\n      operations:\n      - method: GET\n        name: getmetrics\n        description: Helidon All metrics\n        call: helidon.getmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /observe/metrics/application\n      name: getapplicationmetrics\n      operations:\n      - method: GET\n        name: getapplicationmetrics\n        description: Helidon Application metrics\n        call: helidon.getapplicationmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /observe/metrics/vendor\n      name: getvendormetrics\n      operations:\n      - method: GET\n        name: getvendormetrics\n        description: Helidon Vendor metrics\n   \
  \     call: helidon.getvendormetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /observe/metrics/base\n      name: getbasemetrics\n      operations:\n      - method: GET\n        name: getbasemetrics\n        description: Helidon Base metrics\n        call: helidon.getbasemetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /observe/info\n      name: getinfo\n      operations:\n      - method: GET\n        name: getinfo\n        description: Helidon Application info\n        call: helidon.getinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /openapi\n      name: getopenapi\n      operations:\n      - method: GET\n        name: getopenapi\n        description: Helidon OpenAPI document\n        call: helidon.getopenapi\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: helidon-mcp\n    transport:\
  \ http\n    description: MCP adapter for Helidon Observe (Health & Metrics) API for AI agent use.\n    tools:\n    - name: gethealth\n      description: Helidon Overall health status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helidon.gethealth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getliveness\n      description: Helidon Liveness check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helidon.getliveness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreadiness\n      description: Helidon Readiness check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helidon.getreadiness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstartup\n      description: Helidon Startup check\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: helidon.getstartup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmetrics\n      description: Helidon All metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helidon.getmetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapplicationmetrics\n      description: Helidon Application metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helidon.getapplicationmetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvendormetrics\n      description: Helidon Vendor metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helidon.getvendormetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbasemetrics\n   \
  \   description: Helidon Base metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helidon.getbasemetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinfo\n      description: Helidon Application info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helidon.getinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getopenapi\n      description: Helidon OpenAPI document\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helidon.getopenapi\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/helidon/refs/heads/main/capabilities/helidon-capability.yaml
tags:
- Helidon
- API
tools:
- description: Helidon Overall health status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
- description: Helidon Liveness check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getliveness
- description: Helidon Readiness check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreadiness
- description: Helidon Startup check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstartup
- description: Helidon All metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetrics
- description: Helidon Application metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationmetrics
- description: Helidon Vendor metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvendormetrics
- description: Helidon Base metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbasemetrics
- description: Helidon Application info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinfo
- description: Helidon OpenAPI document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getopenapi
---
