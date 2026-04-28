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
- tls hosts and hostname routing.
- retrieve diagnostic overview.
- delete a host resource.
- update an existing route mapping.
- create route
- create a new tlscontext for tls configuration.
- list mappings
- platform
- tls certificate contexts.
- delete a route mapping.
- retrieve a specific module by name.
- delete tls context
- list all rate limits.
- update mapping
- check ready
- delete route
- create a new host resource for tls termination.
- get diagnostics
- update host
- create rate limit
- list hosts
- retrieve a specific tlscontext by name.
- list all module resources for global gateway config.
- create host
- check if the ambassador gateway process is alive.
- retrieve diagnostic overview of the ambassador gateway instance.
- api development
- get rate limit
- update an existing ratelimit.
- list routes
- list modules
- create a new ratelimit resource.
- list rate limits
- list all route mappings in a kubernetes namespace.
- create a new route mapping.
- gateway liveness check.
- check if the ambassador gateway is ready to serve traffic.
- rate limiting configurations.
- update an existing tlscontext.
- update rate limit
- list all tlscontext resources.
- check gateway liveness.
- retrieve a specific ratelimit by name.
- list all hosts.
- list all ratelimit resources.
- get tls context
- update a module resource.
- api route mappings.
- retrieve a specific route mapping by name.
- ingress
- gateways
- get mapping
- mock servers
- kubernetes
- list all route mappings.
- delete mapping
- individual route mapping.
- update module
- delete rate limit
- delete a tlscontext resource.
- get a specific route mapping.
- update tls context
- create a new host.
- create tls context
- get host
- gateway health and diagnostics.
- create a new route mapping for a backend service.
- mocks
- delete a ratelimit resource.
- get route
- retrieve a specific host by name.
- list all tls contexts.
- gateway readiness check.
- ambassador
- api gateway
- list tls contexts
- update route
- update a route mapping.
- list all host resources for tls and hostname routing.
- get module
- check alive
- delete host
- update an existing host resource.
- check gateway readiness.
- create mapping
- testing
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
