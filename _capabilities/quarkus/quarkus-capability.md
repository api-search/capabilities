---
categories: []
consumed_apis: []
description: Quarkus exposes management endpoints for health checks (via SmallRye Health), metrics (via Micrometer/SmallRye Metrics), and OpenAPI documentation. In dev mode, the Dev UI provides a web console with additional introspection endpoints. These endpoints are served under the /q path by default.
layout: capability
name: Quarkus Dev UI & Health/Metrics API
operations:
- description: Quarkus Overall health check
  method: GET
  name: gethealth
  path: /q/health
- description: Quarkus Liveness health check
  method: GET
  name: getliveness
  path: /q/health/live
- description: Quarkus Readiness health check
  method: GET
  name: getreadiness
  path: /q/health/ready
- description: Quarkus Startup health check
  method: GET
  name: getstartup
  path: /q/health/started
- description: Quarkus Application metrics
  method: GET
  name: getmetrics
  path: /q/metrics
- description: Quarkus OpenAPI document
  method: GET
  name: getopenapi
  path: /q/openapi
- description: Quarkus Swagger UI
  method: GET
  name: getswaggerui
  path: /q/swagger-ui
- description: Quarkus Application info
  method: GET
  name: getinfo
  path: /q/info
- description: Quarkus Dev UI dashboard
  method: GET
  name: getdevui
  path: /q/dev-ui
personas: []
provider_name: Quarkus
provider_slug: quarkus
search_terms:
- quarkus startup health check
- getliveness
- getopenapi
- api
- cloud native
- java
- quarkus overall health check
- quarkus
- serverless
- kubernetes
- getstartup
- quarkus liveness health check
- gethealth
- getswaggerui
- frameworks
- quarkus application metrics
- getmetrics
- getinfo
- quarkus application info
- getdevui
- getreadiness
- quarkus dev ui dashboard
- quarkus swagger ui
- quarkus openapi document
- graalvm
- microservices
- quarkus readiness health check
slug: quarkus-capability
source_filename: quarkus-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Quarkus Dev UI & Health/Metrics API\n  description: Quarkus exposes management endpoints for health checks (via SmallRye Health), metrics (via Micrometer/SmallRye\n    Metrics), and OpenAPI documentation. In dev mode, the Dev UI provides a web console with additional introspection endpoints.\n    These endpoints are served under the /q path by default.\n  tags:\n  - Quarkus\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: quarkus\n    baseUri: http://localhost:8080\n    description: Quarkus Dev UI & Health/Metrics API HTTP API.\n    resources:\n    - name: q-health\n      path: /q/health\n      operations:\n      - name: gethealth\n        method: GET\n        description: Quarkus Overall health check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: q-health-live\n      path: /q/health/live\n\
  \      operations:\n      - name: getliveness\n        method: GET\n        description: Quarkus Liveness health check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: q-health-ready\n      path: /q/health/ready\n      operations:\n      - name: getreadiness\n        method: GET\n        description: Quarkus Readiness health check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: q-health-started\n      path: /q/health/started\n      operations:\n      - name: getstartup\n        method: GET\n        description: Quarkus Startup health check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: q-metrics\n      path: /q/metrics\n      operations:\n      - name: getmetrics\n        method: GET\n        description: Quarkus Application\
  \ metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: q-openapi\n      path: /q/openapi\n      operations:\n      - name: getopenapi\n        method: GET\n        description: Quarkus OpenAPI document\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: Response format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: q-swagger-ui\n      path: /q/swagger-ui\n      operations:\n      - name: getswaggerui\n        method: GET\n        description: Quarkus Swagger UI\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: q-info\n      path: /q/info\n      operations:\n      - name: getinfo\n        method: GET\n        description: Quarkus Application info\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: q-dev-ui\n      path: /q/dev-ui\n      operations:\n      - name: getdevui\n        method: GET\n        description: Quarkus Dev UI dashboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: quarkus-rest\n    description: REST adapter for Quarkus Dev UI & Health/Metrics API.\n    resources:\n    - path: /q/health\n      name: gethealth\n      operations:\n      - method: GET\n        name: gethealth\n        description: Quarkus Overall health check\n        call: quarkus.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /q/health/live\n      name: getliveness\n      operations:\n      - method: GET\n        name: getliveness\n        description: Quarkus Liveness health\
  \ check\n        call: quarkus.getliveness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /q/health/ready\n      name: getreadiness\n      operations:\n      - method: GET\n        name: getreadiness\n        description: Quarkus Readiness health check\n        call: quarkus.getreadiness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /q/health/started\n      name: getstartup\n      operations:\n      - method: GET\n        name: getstartup\n        description: Quarkus Startup health check\n        call: quarkus.getstartup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /q/metrics\n      name: getmetrics\n      operations:\n      - method: GET\n        name: getmetrics\n        description: Quarkus Application metrics\n        call: quarkus.getmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /q/openapi\n      name: getopenapi\n\
  \      operations:\n      - method: GET\n        name: getopenapi\n        description: Quarkus OpenAPI document\n        call: quarkus.getopenapi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /q/swagger-ui\n      name: getswaggerui\n      operations:\n      - method: GET\n        name: getswaggerui\n        description: Quarkus Swagger UI\n        call: quarkus.getswaggerui\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /q/info\n      name: getinfo\n      operations:\n      - method: GET\n        name: getinfo\n        description: Quarkus Application info\n        call: quarkus.getinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /q/dev-ui\n      name: getdevui\n      operations:\n      - method: GET\n        name: getdevui\n        description: Quarkus Dev UI dashboard\n        call: quarkus.getdevui\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: quarkus-mcp\n    transport: http\n    description: MCP adapter for Quarkus Dev UI & Health/Metrics API for AI agent use.\n    tools:\n    - name: gethealth\n      description: Quarkus Overall health check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quarkus.gethealth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getliveness\n      description: Quarkus Liveness health check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quarkus.getliveness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreadiness\n      description: Quarkus Readiness health check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quarkus.getreadiness\n      outputParameters:\n      - type: object\n        mapping: $.\n  \
  \  - name: getstartup\n      description: Quarkus Startup health check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quarkus.getstartup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmetrics\n      description: Quarkus Application metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quarkus.getmetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getopenapi\n      description: Quarkus OpenAPI document\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quarkus.getopenapi\n      with:\n        format: tools.format\n      inputParameters:\n      - name: format\n        type: string\n        description: Response format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getswaggerui\n      description: Quarkus Swagger UI\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quarkus.getswaggerui\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinfo\n      description: Quarkus Application info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quarkus.getinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdevui\n      description: Quarkus Dev UI dashboard\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quarkus.getdevui\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/quarkus/refs/heads/main/capabilities/quarkus-capability.yaml
tags:
- Quarkus
- API
tools:
- description: Quarkus Overall health check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
- description: Quarkus Liveness health check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getliveness
- description: Quarkus Readiness health check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreadiness
- description: Quarkus Startup health check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstartup
- description: Quarkus Application metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetrics
- description: Quarkus OpenAPI document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getopenapi
- description: Quarkus Swagger UI
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getswaggerui
- description: Quarkus Application info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinfo
- description: Quarkus Dev UI dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdevui
---
