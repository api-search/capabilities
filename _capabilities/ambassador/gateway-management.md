---
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
- tls certificate contexts.
- list all host resources for tls and hostname routing.
- create a new ratelimit resource.
- check ready
- get host
- api gateway
- retrieve a specific ratelimit by name.
- create rate limit
- tls hosts and hostname routing.
- get module
- create a new host resource for tls termination.
- update an existing host resource.
- update a module resource.
- list modules
- gateway readiness check.
- update an existing tlscontext.
- delete a host resource.
- gateway health and diagnostics.
- create mapping
- delete mapping
- mocks
- api route mappings.
- list all tlscontext resources.
- get route
- update a route mapping.
- retrieve a specific tlscontext by name.
- get rate limit
- list all rate limits.
- list all module resources for global gateway config.
- update rate limit
- create a new host.
- rate limiting configurations.
- list hosts
- list all hosts.
- create a new route mapping.
- retrieve a specific route mapping by name.
- create a new tlscontext for tls configuration.
- list all route mappings in a kubernetes namespace.
- check gateway liveness.
- delete host
- get mapping
- gateway liveness check.
- delete a ratelimit resource.
- kubernetes
- get a specific route mapping.
- delete rate limit
- delete route
- individual route mapping.
- get diagnostics
- gateways
- get tls context
- list tls contexts
- update route
- update an existing ratelimit.
- list routes
- retrieve a specific host by name.
- list all route mappings.
- create tls context
- list mappings
- delete a tlscontext resource.
- ambassador
- update mapping
- mock servers
- check gateway readiness.
- check alive
- list all tls contexts.
- update tls context
- check if the ambassador gateway process is alive.
- check if the ambassador gateway is ready to serve traffic.
- retrieve diagnostic overview of the ambassador gateway instance.
- list all ratelimit resources.
- update host
- api development
- delete tls context
- update module
- create host
- update an existing route mapping.
- platform
- retrieve diagnostic overview.
- create a new route mapping for a backend service.
- retrieve a specific module by name.
- ingress
- testing
- delete a route mapping.
- create route
- list rate limits
slug: gateway-management
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
