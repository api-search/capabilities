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
- delete a route mapping.
- list tls contexts
- get host
- create a new tlscontext for tls configuration.
- list hosts
- mocks
- ambassador
- api development
- rate limiting configurations.
- create a new route mapping for a backend service.
- gateway readiness check.
- retrieve a specific route mapping by name.
- list all tlscontext resources.
- delete rate limit
- list all module resources for global gateway config.
- create a new route mapping.
- update tls context
- list all ratelimit resources.
- delete route
- tls certificate contexts.
- list all route mappings in a kubernetes namespace.
- list all rate limits.
- update an existing host resource.
- create host
- delete a ratelimit resource.
- retrieve a specific tlscontext by name.
- list mappings
- retrieve diagnostic overview.
- individual route mapping.
- update host
- update route
- create a new ratelimit resource.
- create a new host.
- retrieve diagnostic overview of the ambassador gateway instance.
- ingress
- check gateway liveness.
- retrieve a specific ratelimit by name.
- check gateway readiness.
- list all route mappings.
- list modules
- platform
- check if the ambassador gateway is ready to serve traffic.
- update an existing route mapping.
- retrieve a specific host by name.
- update mapping
- create tls context
- gateways
- create a new host resource for tls termination.
- get a specific route mapping.
- check alive
- get mapping
- api route mappings.
- list all host resources for tls and hostname routing.
- list routes
- get rate limit
- delete mapping
- gateway health and diagnostics.
- check ready
- delete a tlscontext resource.
- update a module resource.
- get diagnostics
- list rate limits
- update module
- update rate limit
- create route
- mock servers
- api gateway
- get tls context
- kubernetes
- retrieve a specific module by name.
- get route
- create rate limit
- tls hosts and hostname routing.
- check if the ambassador gateway process is alive.
- gateway liveness check.
- list all tls contexts.
- delete a host resource.
- update a route mapping.
- create mapping
- delete tls context
- testing
- delete host
- update an existing tlscontext.
- list all hosts.
- update an existing ratelimit.
- get module
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
