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
- create host
- create mapping
- api route mappings.
- update mapping
- create a new route mapping.
- update a module resource.
- api development
- gateway liveness check.
- delete mapping
- create a new ratelimit resource.
- delete a route mapping.
- get a specific route mapping.
- list all tls contexts.
- create rate limit
- ingress
- kubernetes
- delete route
- testing
- create a new route mapping for a backend service.
- get tls context
- get diagnostics
- retrieve diagnostic overview.
- create a new host.
- retrieve diagnostic overview of the ambassador gateway instance.
- retrieve a specific module by name.
- list all tlscontext resources.
- retrieve a specific tlscontext by name.
- delete a host resource.
- check alive
- update module
- gateway health and diagnostics.
- platform
- update a route mapping.
- list all rate limits.
- update rate limit
- create a new tlscontext for tls configuration.
- list all route mappings.
- get rate limit
- update an existing tlscontext.
- check if the ambassador gateway is ready to serve traffic.
- delete host
- mock servers
- list routes
- list all route mappings in a kubernetes namespace.
- retrieve a specific ratelimit by name.
- mocks
- gateway readiness check.
- create route
- ambassador
- get module
- check gateway readiness.
- list all ratelimit resources.
- get route
- update an existing ratelimit.
- delete rate limit
- check ready
- get host
- tls hosts and hostname routing.
- delete a tlscontext resource.
- update tls context
- list all hosts.
- update host
- list mappings
- retrieve a specific route mapping by name.
- update an existing host resource.
- individual route mapping.
- list all host resources for tls and hostname routing.
- create tls context
- check gateway liveness.
- list modules
- gateways
- check if the ambassador gateway process is alive.
- delete tls context
- list hosts
- create a new host resource for tls termination.
- tls certificate contexts.
- get mapping
- retrieve a specific host by name.
- list all module resources for global gateway config.
- rate limiting configurations.
- delete a ratelimit resource.
- list tls contexts
- update route
- api gateway
- update an existing route mapping.
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
