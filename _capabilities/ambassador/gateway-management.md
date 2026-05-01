---
categories: []
consumed_apis:
- edge-stack
description: Unified gateway management workflow for platform engineers and DevOps teams to configure API routing, TLS termination, rate limiting, and health monitoring across Ambassador Edge Stack instances.
layout: capability
name: Ambassador Gateway Management
operations:
- description: Retrieve diagnostic overview.
  method: GET
  name: get-diagnostics
  path: /v1/diagnostics
- description: Check gateway readiness.
  method: GET
  name: check-ready
  path: /v1/health/ready
- description: Check gateway liveness.
  method: GET
  name: check-alive
  path: /v1/health/alive
- description: List all route mappings.
  method: GET
  name: list-routes
  path: /v1/routes
- description: Create a new route mapping.
  method: POST
  name: create-route
  path: /v1/routes
- description: Get a specific route mapping.
  method: GET
  name: get-route
  path: /v1/routes/{name}
- description: Update a route mapping.
  method: PUT
  name: update-route
  path: /v1/routes/{name}
- description: Delete a route mapping.
  method: DELETE
  name: delete-route
  path: /v1/routes/{name}
- description: List all hosts.
  method: GET
  name: list-hosts
  path: /v1/hosts
- description: Create a new host.
  method: POST
  name: create-host
  path: /v1/hosts
- description: List all TLS contexts.
  method: GET
  name: list-tls-contexts
  path: /v1/tls-contexts
- description: List all rate limits.
  method: GET
  name: list-rate-limits
  path: /v1/rate-limits
personas: []
provider_name: Ambassador
provider_slug: ambassador
search_terms:
- update module
- check if the ambassador gateway is ready to serve traffic.
- retrieve a specific route mapping by name.
- api route mappings.
- create host
- update rate limit
- update mapping
- check gateway liveness.
- check if the ambassador gateway process is alive.
- testing
- list all ratelimit resources.
- mock servers
- update an existing tlscontext.
- list modules
- update a route mapping.
- create a new host resource for tls termination.
- delete tls context
- retrieve a specific module by name.
- mocks
- retrieve diagnostic overview.
- tls hosts and hostname routing.
- create route
- delete mapping
- api gateway
- list mappings
- api development
- update tls context
- delete a route mapping.
- check gateway readiness.
- list routes
- update an existing ratelimit.
- ingress
- create a new tlscontext for tls configuration.
- update an existing route mapping.
- delete a host resource.
- create a new ratelimit resource.
- check alive
- delete rate limit
- get rate limit
- retrieve a specific ratelimit by name.
- platform
- create a new route mapping for a backend service.
- create a new route mapping.
- update a module resource.
- list all hosts.
- update an existing host resource.
- individual route mapping.
- list all tls contexts.
- get host
- list all host resources for tls and hostname routing.
- get a specific route mapping.
- get module
- retrieve a specific host by name.
- retrieve diagnostic overview of the ambassador gateway instance.
- delete a tlscontext resource.
- get route
- create mapping
- list hosts
- create rate limit
- get diagnostics
- gateway readiness check.
- gateway health and diagnostics.
- get mapping
- list tls contexts
- update route
- get tls context
- kubernetes
- gateway liveness check.
- create tls context
- delete a ratelimit resource.
- list all route mappings in a kubernetes namespace.
- rate limiting configurations.
- tls certificate contexts.
- delete host
- check ready
- delete route
- list rate limits
- update host
- ambassador
- list all route mappings.
- retrieve a specific tlscontext by name.
- list all module resources for global gateway config.
- create a new host.
- gateways
- list all tlscontext resources.
- list all rate limits.
slug: gateway-management
source_filename: gateway-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Ambassador Gateway Management\"\n  description: \"Unified gateway management workflow for platform engineers and DevOps teams to configure API routing, TLS termination, rate limiting, and health monitoring across Ambassador Edge Stack instances.\"\n  tags:\n    - Ambassador\n    - API Gateway\n    - Kubernetes\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMBASSADOR_API_TOKEN: AMBASSADOR_API_TOKEN\n\ncapability:\n  consumes:\n    - import: edge-stack\n      location: ./shared/edge-stack.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: gateway-management-api\n      description: \"Unified REST API for managing Ambassador Edge Stack gateway resources.\"\n      resources:\n        - path: /v1/diagnostics\n          name: diagnostics\n          description: \"Gateway health and diagnostics.\"\n          operations:\n            - method: GET\n         \
  \     name: get-diagnostics\n              description: \"Retrieve diagnostic overview.\"\n              call: \"edge-stack.get-diagnostics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/health/ready\n          name: readiness\n          description: \"Gateway readiness check.\"\n          operations:\n            - method: GET\n              name: check-ready\n              description: \"Check gateway readiness.\"\n              call: \"edge-stack.check-ready\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/health/alive\n          name: liveness\n          description: \"Gateway liveness check.\"\n          operations:\n            - method: GET\n              name: check-alive\n              description: \"Check gateway liveness.\"\n              call: \"edge-stack.check-alive\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/routes\n          name: routes\n          description: \"API route mappings.\"\n          operations:\n            - method: GET\n              name: list-routes\n              description: \"List all route mappings.\"\n              call: \"edge-stack.list-mappings\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-route\n              description: \"Create a new route mapping.\"\n              call: \"edge-stack.create-mapping\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/routes/{name}\n          name: route\n          description: \"Individual route mapping.\"\n          operations:\n            - method:\
  \ GET\n              name: get-route\n              description: \"Get a specific route mapping.\"\n              call: \"edge-stack.get-mapping\"\n              with:\n                namespace: \"rest.namespace\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-route\n              description: \"Update a route mapping.\"\n              call: \"edge-stack.update-mapping\"\n              with:\n                namespace: \"rest.namespace\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-route\n              description: \"Delete a route mapping.\"\n              call: \"edge-stack.delete-mapping\"\n              with:\n                namespace: \"rest.namespace\"\n                name: \"rest.name\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hosts\n          name: hosts\n          description: \"TLS hosts and hostname routing.\"\n          operations:\n            - method: GET\n              name: list-hosts\n              description: \"List all hosts.\"\n              call: \"edge-stack.list-hosts\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-host\n              description: \"Create a new host.\"\n              call: \"edge-stack.create-host\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tls-contexts\n          name: tls-contexts\n          description: \"TLS certificate contexts.\"\
  \n          operations:\n            - method: GET\n              name: list-tls-contexts\n              description: \"List all TLS contexts.\"\n              call: \"edge-stack.list-tls-contexts\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rate-limits\n          name: rate-limits\n          description: \"Rate limiting configurations.\"\n          operations:\n            - method: GET\n              name: list-rate-limits\n              description: \"List all rate limits.\"\n              call: \"edge-stack.list-rate-limits\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: gateway-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ Ambassador Edge Stack gateway management.\"\n      tools:\n        - name: get-diagnostics\n          description: \"Retrieve diagnostic overview of the Ambassador gateway instance.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"edge-stack.get-diagnostics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-ready\n          description: \"Check if the Ambassador gateway is ready to serve traffic.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.check-ready\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-alive\n          description: \"Check if the Ambassador gateway process is alive.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.check-alive\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-mappings\n\
  \          description: \"List all route mappings in a Kubernetes namespace.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.list-mappings\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-mapping\n          description: \"Create a new route mapping for a backend service.\"\n          hints:\n            readOnly: false\n          call: \"edge-stack.create-mapping\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-mapping\n          description: \"Retrieve a specific route mapping by name.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.get-mapping\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n           \
  \ - type: object\n              mapping: \"$.\"\n        - name: update-mapping\n          description: \"Update an existing route mapping.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"edge-stack.update-mapping\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-mapping\n          description: \"Delete a route mapping.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"edge-stack.delete-mapping\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-hosts\n          description: \"List all Host resources for TLS and hostname routing.\"\n          hints:\n            readOnly: true\n\
  \          call: \"edge-stack.list-hosts\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-host\n          description: \"Create a new Host resource for TLS termination.\"\n          hints:\n            readOnly: false\n          call: \"edge-stack.create-host\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-host\n          description: \"Retrieve a specific Host by name.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.get-host\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-host\n          description: \"Update an existing Host resource.\"\n          hints:\n\
  \            readOnly: false\n            idempotent: true\n          call: \"edge-stack.update-host\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-host\n          description: \"Delete a Host resource.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"edge-stack.delete-host\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tls-contexts\n          description: \"List all TLSContext resources.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.list-tls-contexts\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: create-tls-context\n          description: \"Create a new TLSContext for TLS configuration.\"\n          hints:\n            readOnly: false\n          call: \"edge-stack.create-tls-context\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-tls-context\n          description: \"Retrieve a specific TLSContext by name.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.get-tls-context\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-tls-context\n          description: \"Update an existing TLSContext.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"edge-stack.update-tls-context\"\n          with:\n            namespace:\
  \ \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-tls-context\n          description: \"Delete a TLSContext resource.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"edge-stack.delete-tls-context\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-rate-limits\n          description: \"List all RateLimit resources.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.list-rate-limits\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-rate-limit\n          description: \"Create a new RateLimit resource.\"\n          hints:\n\
  \            readOnly: false\n          call: \"edge-stack.create-rate-limit\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-rate-limit\n          description: \"Retrieve a specific RateLimit by name.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.get-rate-limit\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-rate-limit\n          description: \"Update an existing RateLimit.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"edge-stack.update-rate-limit\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: delete-rate-limit\n          description: \"Delete a RateLimit resource.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"edge-stack.delete-rate-limit\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-modules\n          description: \"List all Module resources for global gateway config.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.list-modules\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-module\n          description: \"Retrieve a specific Module by name.\"\n          hints:\n            readOnly: true\n          call: \"edge-stack.get-module\"\n          with:\n            namespace: \"tools.namespace\"\
  \n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-module\n          description: \"Update a Module resource.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"edge-stack.update-module\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ambassador/refs/heads/main/capabilities/gateway-management.yaml
tags:
- Ambassador
- API Gateway
- Kubernetes
tools:
- description: Retrieve diagnostic overview of the Ambassador gateway instance.
  hints:
    openWorld: true
    readOnly: true
  name: get-diagnostics
- description: Check if the Ambassador gateway is ready to serve traffic.
  hints:
    readOnly: true
  name: check-ready
- description: Check if the Ambassador gateway process is alive.
  hints:
    readOnly: true
  name: check-alive
- description: List all route mappings in a Kubernetes namespace.
  hints:
    readOnly: true
  name: list-mappings
- description: Create a new route mapping for a backend service.
  hints:
    readOnly: false
  name: create-mapping
- description: Retrieve a specific route mapping by name.
  hints:
    readOnly: true
  name: get-mapping
- description: Update an existing route mapping.
  hints:
    idempotent: true
    readOnly: false
  name: update-mapping
- description: Delete a route mapping.
  hints:
    destructive: true
    idempotent: true
  name: delete-mapping
- description: List all Host resources for TLS and hostname routing.
  hints:
    readOnly: true
  name: list-hosts
- description: Create a new Host resource for TLS termination.
  hints:
    readOnly: false
  name: create-host
- description: Retrieve a specific Host by name.
  hints:
    readOnly: true
  name: get-host
- description: Update an existing Host resource.
  hints:
    idempotent: true
    readOnly: false
  name: update-host
- description: Delete a Host resource.
  hints:
    destructive: true
    idempotent: true
  name: delete-host
- description: List all TLSContext resources.
  hints:
    readOnly: true
  name: list-tls-contexts
- description: Create a new TLSContext for TLS configuration.
  hints:
    readOnly: false
  name: create-tls-context
- description: Retrieve a specific TLSContext by name.
  hints:
    readOnly: true
  name: get-tls-context
- description: Update an existing TLSContext.
  hints:
    idempotent: true
    readOnly: false
  name: update-tls-context
- description: Delete a TLSContext resource.
  hints:
    destructive: true
    idempotent: true
  name: delete-tls-context
- description: List all RateLimit resources.
  hints:
    readOnly: true
  name: list-rate-limits
- description: Create a new RateLimit resource.
  hints:
    readOnly: false
  name: create-rate-limit
- description: Retrieve a specific RateLimit by name.
  hints:
    readOnly: true
  name: get-rate-limit
- description: Update an existing RateLimit.
  hints:
    idempotent: true
    readOnly: false
  name: update-rate-limit
- description: Delete a RateLimit resource.
  hints:
    destructive: true
    idempotent: true
  name: delete-rate-limit
- description: List all Module resources for global gateway config.
  hints:
    readOnly: true
  name: list-modules
- description: Retrieve a specific Module by name.
  hints:
    readOnly: true
  name: get-module
- description: Update a Module resource.
  hints:
    idempotent: true
    readOnly: false
  name: update-module
---
