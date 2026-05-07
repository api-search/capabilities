---
categories: []
consumed_apis: []
description: Unified workflow capability for operating and observing Traefik reverse proxy and API gateway instances. Combines configuration inspection, routing management, health monitoring, and traffic observability for platform engineers, DevOps teams, and site reliability engineers.
layout: capability
name: Traefik Proxy Operations
operations:
- description: Get the current Traefik version and codename.
  method: GET
  name: get-version
  path: /v1/version
- description: Get overview statistics for all routing configuration.
  method: GET
  name: get-overview
  path: /v1/overview
- description: List all configured entry points.
  method: GET
  name: list-entry-points
  path: /v1/entry-points
- description: List all HTTP routers.
  method: GET
  name: list-http-routers
  path: /v1/http/routers
- description: List all HTTP backend services.
  method: GET
  name: list-http-services
  path: /v1/http/services
- description: List all HTTP middlewares.
  method: GET
  name: list-http-middlewares
  path: /v1/http/middlewares
- description: List all TCP routers.
  method: GET
  name: list-tcp-routers
  path: /v1/tcp/routers
- description: List all TCP services.
  method: GET
  name: list-tcp-services
  path: /v1/tcp/services
- description: List all UDP routers.
  method: GET
  name: list-udp-routers
  path: /v1/udp/routers
- description: Liveness health check.
  method: GET
  name: ping
  path: /v1/health
personas: []
provider_name: Traefik
provider_slug: traefik
search_terms:
- list all udp routers for udp traffic routing.
- udp routing configuration.
- list all tcp routers.
- list all http routers.
- liveness health check.
- list all configured traefik entry points showing which ports and protocols are exposed.
- perform a liveness health check against the traefik instance.
- list http services
- tcp backend services.
- get overview
- list all http routers with routing rules, entry points, middleware chains, and service assignments.
- list all tcp services.
- configuration
- get the current traefik version, codename, and start date.
- http backend services.
- reverse proxy
- list all http backend services.
- get routing overview
- list tcp routers
- list all udp routers.
- open source
- list tcp services
- list all tcp routers for non-http traffic routing.
- check health
- traefik version information.
- traefik routing configuration overview.
- http middleware chain configurations.
- list entry points
- list http routers
- kubernetes
- http router rules and configuration.
- observability
- list http middlewares
- list all http middlewares showing type, configuration, and which routers use them.
- api gateway
- list all http middlewares.
- traefik
- traefik health check.
- list all http backend services showing load balancer configuration and server health.
- get overview statistics for all routing configuration.
- tcp routing configuration.
- get version
- list udp routers
- get a high-level overview of all traefik routing configuration including router and service counts.
- get traefik version
- ping
- network entry points.
- get the current traefik version and codename.
- load balancer
- list all tcp backend services.
- list all configured entry points.
slug: proxy-operations
source_filename: proxy-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Traefik Proxy Operations\n  description: Unified workflow capability for operating and observing Traefik reverse proxy and API gateway instances. Combines\n    configuration inspection, routing management, health monitoring, and traffic observability for platform engineers, DevOps\n    teams, and site reliability engineers.\n  tags:\n  - API Gateway\n  - Configuration\n  - Kubernetes\n  - Load Balancer\n  - Observability\n  - Reverse Proxy\n  - Traefik\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRAEFIK_API_URL: TRAEFIK_API_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: traefik-api\n    baseUri: '{{env.TRAEFIK_API_URL}}'\n    description: Traefik REST API for inspecting routing configuration and runtime state.\n    resources:\n    - name: overview\n      path: /api\n      description: Overview, version, and raw configuration data.\n      operations:\n      - name: get-version\n\
  \        method: GET\n        description: Get the running Traefik version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-overview\n        method: GET\n        description: Get overview statistics for routers, services, and middlewares.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-raw-data\n        method: GET\n        description: Get complete raw dynamic configuration from all providers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entrypoints\n      path: /api/entrypoints\n      description: Entry points configuration.\n      operations:\n      - name: list-entry-points\n        method: GET\n        description: List all configured Traefik entry points.\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-entry-point\n        method: GET\n        description: Get a specific entry point by name.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Entry point name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-routers\n      path: /api/http/routers\n      description: HTTP routers configuration.\n      operations:\n      - name: list-http-routers\n        method: GET\n        description: List all HTTP routers.\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Filter by name.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by\
  \ status (enabled/disabled).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-http-router\n        method: GET\n        description: Get a specific HTTP router.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Router name in format name@provider.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-services\n      path: /api/http/services\n      description: HTTP services configuration.\n      operations:\n      - name: list-http-services\n        method: GET\n        description: List all HTTP services.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-http-service\n        method: GET\n        description: Get a specific\
  \ HTTP service.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Service name in format name@provider.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: http-middlewares\n      path: /api/http/middlewares\n      description: HTTP middlewares configuration.\n      operations:\n      - name: list-http-middlewares\n        method: GET\n        description: List all HTTP middlewares.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-http-middleware\n        method: GET\n        description: Get a specific HTTP middleware.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Middleware name in format name@provider.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tcp\n      path: /api/tcp\n      description: TCP routers, services, and middlewares.\n      operations:\n      - name: list-tcp-routers\n        method: GET\n        description: List all TCP routers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-tcp-router\n        method: GET\n        description: Get a specific TCP router.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: TCP router name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-tcp-services\n        method: GET\n        description: List all TCP services.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: array\n          value: $.\n    - name: udp\n      path: /api/udp\n      description: UDP routers and services.\n      operations:\n      - name: list-udp-routers\n        method: GET\n        description: List all UDP routers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: list-udp-services\n        method: GET\n        description: List all UDP services.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: health\n      path: /ping\n      description: Health check endpoint.\n      operations:\n      - name: ping\n        method: GET\n        description: Health check ping — returns 200 OK when Traefik is alive.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n\
  \    namespace: traefik-proxy-operations-api\n    description: Unified REST API for Traefik proxy configuration inspection and health monitoring.\n    resources:\n    - path: /v1/version\n      name: version\n      description: Traefik version information.\n      operations:\n      - method: GET\n        name: get-version\n        description: Get the current Traefik version and codename.\n        call: traefik-api.get-version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/overview\n      name: overview\n      description: Traefik routing configuration overview.\n      operations:\n      - method: GET\n        name: get-overview\n        description: Get overview statistics for all routing configuration.\n        call: traefik-api.get-overview\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entry-points\n      name: entry-points\n      description: Network entry points.\n      operations:\n      - method:\
  \ GET\n        name: list-entry-points\n        description: List all configured entry points.\n        call: traefik-api.list-entry-points\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/http/routers\n      name: http-routers\n      description: HTTP router rules and configuration.\n      operations:\n      - method: GET\n        name: list-http-routers\n        description: List all HTTP routers.\n        call: traefik-api.list-http-routers\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/http/services\n      name: http-services\n      description: HTTP backend services.\n      operations:\n      - method: GET\n        name: list-http-services\n        description: List all HTTP backend services.\n        call: traefik-api.list-http-services\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/http/middlewares\n      name: http-middlewares\n      description: HTTP middleware\
  \ chain configurations.\n      operations:\n      - method: GET\n        name: list-http-middlewares\n        description: List all HTTP middlewares.\n        call: traefik-api.list-http-middlewares\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/tcp/routers\n      name: tcp-routers\n      description: TCP routing configuration.\n      operations:\n      - method: GET\n        name: list-tcp-routers\n        description: List all TCP routers.\n        call: traefik-api.list-tcp-routers\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/tcp/services\n      name: tcp-services\n      description: TCP backend services.\n      operations:\n      - method: GET\n        name: list-tcp-services\n        description: List all TCP services.\n        call: traefik-api.list-tcp-services\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/udp/routers\n      name: udp-routers\n    \
  \  description: UDP routing configuration.\n      operations:\n      - method: GET\n        name: list-udp-routers\n        description: List all UDP routers.\n        call: traefik-api.list-udp-routers\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/health\n      name: health\n      description: Traefik health check.\n      operations:\n      - method: GET\n        name: ping\n        description: Liveness health check.\n        call: traefik-api.ping\n        outputParameters:\n        - type: string\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: traefik-proxy-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted Traefik proxy management, configuration inspection, and routing analysis.\n    tools:\n    - name: get-traefik-version\n      description: Get the current Traefik version, codename, and start date.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traefik-api.get-version\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-routing-overview\n      description: Get a high-level overview of all Traefik routing configuration including router and service counts.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traefik-api.get-overview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-entry-points\n      description: List all configured Traefik entry points showing which ports and protocols are exposed.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traefik-api.list-entry-points\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-http-routers\n      description: List all HTTP routers with routing rules, entry points, middleware chains, and service assignments.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traefik-api.list-http-routers\n      outputParameters:\n      - type:\
  \ array\n        mapping: $.\n    - name: list-http-services\n      description: List all HTTP backend services showing load balancer configuration and server health.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traefik-api.list-http-services\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-http-middlewares\n      description: List all HTTP middlewares showing type, configuration, and which routers use them.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traefik-api.list-http-middlewares\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-tcp-routers\n      description: List all TCP routers for non-HTTP traffic routing.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traefik-api.list-tcp-routers\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-tcp-services\n      description: List all TCP backend\
  \ services.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traefik-api.list-tcp-services\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-udp-routers\n      description: List all UDP routers for UDP traffic routing.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traefik-api.list-udp-routers\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: check-health\n      description: Perform a liveness health check against the Traefik instance.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: traefik-api.ping\n      outputParameters:\n      - type: string\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/traefik/refs/heads/main/capabilities/proxy-operations.yaml
tags:
- API Gateway
- Configuration
- Kubernetes
- Load Balancer
- Observability
- Reverse Proxy
- Traefik
tools:
- description: Get the current Traefik version, codename, and start date.
  hints:
    idempotent: true
    readOnly: true
  name: get-traefik-version
- description: Get a high-level overview of all Traefik routing configuration including router and service counts.
  hints:
    idempotent: true
    readOnly: true
  name: get-routing-overview
- description: List all configured Traefik entry points showing which ports and protocols are exposed.
  hints:
    idempotent: true
    readOnly: true
  name: list-entry-points
- description: List all HTTP routers with routing rules, entry points, middleware chains, and service assignments.
  hints:
    idempotent: true
    readOnly: true
  name: list-http-routers
- description: List all HTTP backend services showing load balancer configuration and server health.
  hints:
    idempotent: true
    readOnly: true
  name: list-http-services
- description: List all HTTP middlewares showing type, configuration, and which routers use them.
  hints:
    idempotent: true
    readOnly: true
  name: list-http-middlewares
- description: List all TCP routers for non-HTTP traffic routing.
  hints:
    idempotent: true
    readOnly: true
  name: list-tcp-routers
- description: List all TCP backend services.
  hints:
    idempotent: true
    readOnly: true
  name: list-tcp-services
- description: List all UDP routers for UDP traffic routing.
  hints:
    idempotent: true
    readOnly: true
  name: list-udp-routers
- description: Perform a liveness health check against the Traefik instance.
  hints:
    idempotent: true
    readOnly: true
  name: check-health
---
