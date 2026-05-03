---
api_specs:
- filename: traefik-api-openapi.yml
  format: yaml
  label: traefik-api
  slug: traefik-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/traefik/refs/heads/main/openapi/traefik-api-openapi.yml
categories: []
consumed_apis:
- traefik-api
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
- list all http backend services.
- list all http middlewares showing type, configuration, and which routers use them.
- list all tcp routers for non-http traffic routing.
- load balancer
- get overview
- tcp backend services.
- open source
- list all http routers with routing rules, entry points, middleware chains, and service assignments.
- traefik routing configuration overview.
- http backend services.
- traefik
- list all http backend services showing load balancer configuration and server health.
- list all configured entry points.
- list all tcp backend services.
- list tcp services
- list udp routers
- get the current traefik version, codename, and start date.
- liveness health check.
- get routing overview
- kubernetes
- get the current traefik version and codename.
- perform a liveness health check against the traefik instance.
- configuration
- check health
- list all udp routers for udp traffic routing.
- udp routing configuration.
- api gateway
- list all configured traefik entry points showing which ports and protocols are exposed.
- reverse proxy
- list http services
- list all tcp services.
- tcp routing configuration.
- ping
- traefik version information.
- list all udp routers.
- list entry points
- list all http middlewares.
- get overview statistics for all routing configuration.
- list http middlewares
- observability
- http middleware chain configurations.
- http router rules and configuration.
- list all tcp routers.
- traefik health check.
- get a high-level overview of all traefik routing configuration including router and service counts.
- list http routers
- network entry points.
- get traefik version
- get version
- list tcp routers
- list all http routers.
slug: proxy-operations
source_filename: proxy-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Traefik Proxy Operations\"\n  description: \"Unified workflow capability for operating and observing Traefik reverse proxy and API gateway instances. Combines configuration inspection, routing management, health monitoring, and traffic observability for platform engineers, DevOps teams, and site reliability engineers.\"\n  tags:\n    - API Gateway\n    - Configuration\n    - Kubernetes\n    - Load Balancer\n    - Observability\n    - Reverse Proxy\n    - Traefik\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRAEFIK_API_URL: TRAEFIK_API_URL\n\ncapability:\n  consumes:\n    - import: traefik-api\n      location: ./shared/traefik-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: traefik-proxy-operations-api\n      description: \"Unified REST API for Traefik proxy configuration inspection and health monitoring.\"\n      resources:\n        - path: /v1/version\n\
  \          name: version\n          description: \"Traefik version information.\"\n          operations:\n            - method: GET\n              name: get-version\n              description: \"Get the current Traefik version and codename.\"\n              call: \"traefik-api.get-version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/overview\n          name: overview\n          description: \"Traefik routing configuration overview.\"\n          operations:\n            - method: GET\n              name: get-overview\n              description: \"Get overview statistics for all routing configuration.\"\n              call: \"traefik-api.get-overview\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/entry-points\n          name: entry-points\n          description: \"Network entry points.\"\n          operations:\n            - method:\
  \ GET\n              name: list-entry-points\n              description: \"List all configured entry points.\"\n              call: \"traefik-api.list-entry-points\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/http/routers\n          name: http-routers\n          description: \"HTTP router rules and configuration.\"\n          operations:\n            - method: GET\n              name: list-http-routers\n              description: \"List all HTTP routers.\"\n              call: \"traefik-api.list-http-routers\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/http/services\n          name: http-services\n          description: \"HTTP backend services.\"\n          operations:\n            - method: GET\n              name: list-http-services\n              description: \"List all HTTP backend services.\"\n              call: \"traefik-api.list-http-services\"\
  \n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/http/middlewares\n          name: http-middlewares\n          description: \"HTTP middleware chain configurations.\"\n          operations:\n            - method: GET\n              name: list-http-middlewares\n              description: \"List all HTTP middlewares.\"\n              call: \"traefik-api.list-http-middlewares\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/tcp/routers\n          name: tcp-routers\n          description: \"TCP routing configuration.\"\n          operations:\n            - method: GET\n              name: list-tcp-routers\n              description: \"List all TCP routers.\"\n              call: \"traefik-api.list-tcp-routers\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/tcp/services\n\
  \          name: tcp-services\n          description: \"TCP backend services.\"\n          operations:\n            - method: GET\n              name: list-tcp-services\n              description: \"List all TCP services.\"\n              call: \"traefik-api.list-tcp-services\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/udp/routers\n          name: udp-routers\n          description: \"UDP routing configuration.\"\n          operations:\n            - method: GET\n              name: list-udp-routers\n              description: \"List all UDP routers.\"\n              call: \"traefik-api.list-udp-routers\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/health\n          name: health\n          description: \"Traefik health check.\"\n          operations:\n            - method: GET\n              name: ping\n              description:\
  \ \"Liveness health check.\"\n              call: \"traefik-api.ping\"\n              outputParameters:\n                - type: string\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: traefik-proxy-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Traefik proxy management, configuration inspection, and routing analysis.\"\n      tools:\n        - name: get-traefik-version\n          description: \"Get the current Traefik version, codename, and start date.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traefik-api.get-version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-routing-overview\n          description: \"Get a high-level overview of all Traefik routing configuration including router and service counts.\"\n          hints:\n            readOnly: true\n            idempotent: true\n    \
  \      call: \"traefik-api.get-overview\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-entry-points\n          description: \"List all configured Traefik entry points showing which ports and protocols are exposed.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traefik-api.list-entry-points\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-http-routers\n          description: \"List all HTTP routers with routing rules, entry points, middleware chains, and service assignments.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traefik-api.list-http-routers\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-http-services\n          description: \"List all HTTP backend services showing load balancer configuration\
  \ and server health.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traefik-api.list-http-services\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-http-middlewares\n          description: \"List all HTTP middlewares showing type, configuration, and which routers use them.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traefik-api.list-http-middlewares\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-tcp-routers\n          description: \"List all TCP routers for non-HTTP traffic routing.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traefik-api.list-tcp-routers\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-tcp-services\n          description: \"\
  List all TCP backend services.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traefik-api.list-tcp-services\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-udp-routers\n          description: \"List all UDP routers for UDP traffic routing.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traefik-api.list-udp-routers\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: check-health\n          description: \"Perform a liveness health check against the Traefik instance.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"traefik-api.ping\"\n          outputParameters:\n            - type: string\n              mapping: \"$.\"\n"
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
