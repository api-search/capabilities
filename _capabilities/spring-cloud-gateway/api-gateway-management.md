---
categories: []
consumed_apis: []
description: Unified capability for managing an API gateway built on Spring Cloud Gateway. Enables dynamic route creation, predicate and filter management, cache refresh, and runtime gateway inspection for platform engineers and API teams.
layout: capability
name: Spring Cloud Gateway API Gateway Management
operations:
- description: List all gateway routes
  method: GET
  name: list-routes
  path: /v1/routes
- description: Create a new gateway route
  method: POST
  name: create-route
  path: /v1/routes
- description: Get route by ID
  method: GET
  name: get-route
  path: /v1/routes/{id}
- description: Update route definition
  method: PUT
  name: update-route
  path: /v1/routes/{id}
- description: Remove route from gateway
  method: DELETE
  name: delete-route
  path: /v1/routes/{id}
- description: Refresh route configuration cache
  method: POST
  name: refresh-routes
  path: /v1/routes/refresh
- description: List global filters
  method: GET
  name: list-global-filters
  path: /v1/filters
- description: List route filter factories
  method: GET
  name: list-filter-factories
  path: /v1/filter-factories
- description: List route predicate factories
  method: GET
  name: list-predicate-factories
  path: /v1/predicate-factories
personas: []
provider_name: Spring Cloud Gateway
provider_slug: spring-cloud-gateway
search_terms:
- discover filter options
- devops
- delete route
- refresh route configuration cache
- list all gateway routes
- gateway route management
- get route
- deploy a new gateway route with path/host/method predicates and filters such as stripprefix, addrequestheader, circuitbreaker, requestratelimiter
- modify route
- create a new gateway route
- create route
- refresh routes
- update route definition
- available predicate factories
- audit all global filters applied to every request, including their execution order
- discover all available routepredicatefactory options for defining traffic routing rules
- list global filters
- remove route
- discover all available gatewayfilter factory options for configuring request/response transformation
- available filter factories
- route management
- list route filter factories
- inspect a specific gateway route definition by id
- discover predicate options
- list route predicate factories
- routing
- inspect all currently configured gateway routes including predicates, filters, uris, ordering, and metadata
- api gateway
- list routes
- remove a gateway route, stopping traffic forwarding for matching requests
- sync route config
- circuit breaker
- spring
- get route by id
- modify an existing gateway route's destination uri, matching predicates, or applied filters without downtime
- deploy route
- list predicate factories
- load balancing
- route cache management
- rate limiting
- spring cloud
- spring webflux
- synchronize the gateway route cache with the current configuration source
- filter management
- inspect route
- update route
- list filter factories
- individual route operations
- audit global filters
- inspect all routes
- remove route from gateway
- microservices
- platform engineering
slug: api-gateway-management
source_filename: api-gateway-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Cloud Gateway API Gateway Management\n  description: Unified capability for managing an API gateway built on Spring Cloud Gateway. Enables dynamic route creation,\n    predicate and filter management, cache refresh, and runtime gateway inspection for platform engineers and API teams.\n  tags:\n  - Spring Cloud\n  - API Gateway\n  - Route Management\n  - Platform Engineering\n  - Microservices\n  - DevOps\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPRING_GATEWAY_ACTUATOR_URL: SPRING_GATEWAY_ACTUATOR_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: spring-cloud-gateway\n    baseUri: '{{SPRING_GATEWAY_ACTUATOR_URL}}'\n    description: Spring Cloud Gateway Actuator API for runtime route management\n    resources:\n    - name: routes\n      path: /routes\n      description: Gateway route definitions\n      operations:\n      - name: list-routes\n        method: GET\n      \
  \  description: List all gateway routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-route\n        method: POST\n        description: Create a new route definition\n        body:\n          type: json\n          data:\n            id: '{{tools.routeId}}'\n            uri: '{{tools.uri}}'\n            predicates: '{{tools.predicates}}'\n            filters: '{{tools.filters}}'\n            order: '{{tools.order}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-route\n        method: GET\n        description: Get a specific route by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Route identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: update-route\n        method: PUT\n        description: Update a route definition\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Route identifier\n        body:\n          type: json\n          data:\n            uri: '{{tools.uri}}'\n            predicates: '{{tools.predicates}}'\n            filters: '{{tools.filters}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-route\n        method: DELETE\n        description: Delete a route definition\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Route identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cache-refresh\n\
  \      path: /refresh\n      description: Route cache refresh\n      operations:\n      - name: refresh-routes\n        method: POST\n        description: Force refresh of the routes cache\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: global-filters\n      path: /globalfilters\n      description: Global gateway filters\n      operations:\n      - name: list-global-filters\n        method: GET\n        description: List all global filters with their ordering\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: route-filters\n      path: /routefilters\n      description: Route filter factories\n      operations:\n      - name: list-route-filter-factories\n        method: GET\n        description: List all available route filter factories\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: predicates\n      path: /routepredicates\n      description: Route predicate factories\n      operations:\n      - name: list-predicate-factories\n        method: GET\n        description: List all available route predicate factories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: api-gateway-management-api\n    description: Unified REST API for API gateway lifecycle management.\n    resources:\n    - path: /v1/routes\n      name: routes\n      description: Gateway route management\n      operations:\n      - method: GET\n        name: list-routes\n        description: List all gateway routes\n        call: spring-cloud-gateway.list-routes\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-route\n        description:\
  \ Create a new gateway route\n        call: spring-cloud-gateway.create-route\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/routes/{id}\n      name: route-detail\n      description: Individual route operations\n      operations:\n      - method: GET\n        name: get-route\n        description: Get route by ID\n        call: spring-cloud-gateway.get-route\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-route\n        description: Update route definition\n        call: spring-cloud-gateway.update-route\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-route\n        description: Remove route from gateway\n        call: spring-cloud-gateway.delete-route\n        with:\n          id: rest.id\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/routes/refresh\n      name: route-refresh\n      description: Route cache management\n      operations:\n      - method: POST\n        name: refresh-routes\n        description: Refresh route configuration cache\n        call: spring-cloud-gateway.refresh-routes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/filters\n      name: filters\n      description: Filter management\n      operations:\n      - method: GET\n        name: list-global-filters\n        description: List global filters\n        call: spring-cloud-gateway.list-global-filters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/filter-factories\n      name: filter-factories\n      description: Available filter factories\n      operations:\n      - method: GET\n        name: list-filter-factories\n        description: List route filter factories\n        call: spring-cloud-gateway.list-route-filter-factories\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/predicate-factories\n      name: predicate-factories\n      description: Available predicate factories\n      operations:\n      - method: GET\n        name: list-predicate-factories\n        description: List route predicate factories\n        call: spring-cloud-gateway.list-predicate-factories\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: api-gateway-management-mcp\n    transport: http\n    description: MCP server for AI-assisted API gateway management and troubleshooting.\n    tools:\n    - name: inspect-all-routes\n      description: Inspect all currently configured gateway routes including predicates, filters, URIs, ordering, and metadata\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-cloud-gateway.list-routes\n      outputParameters:\n      - type: object\n        mapping: $.\n  \
  \  - name: inspect-route\n      description: Inspect a specific gateway route definition by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-cloud-gateway.get-route\n      with:\n        id: tools.routeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-route\n      description: Deploy a new gateway route with Path/Host/Method predicates and filters such as StripPrefix, AddRequestHeader,\n        CircuitBreaker, RequestRateLimiter\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: spring-cloud-gateway.create-route\n      with:\n        routeId: tools.routeId\n        uri: tools.destinationUri\n        predicates: tools.predicates\n        filters: tools.filters\n        order: tools.priority\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modify-route\n      description: Modify an existing gateway route's destination URI,\
  \ matching predicates, or applied filters without downtime\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: spring-cloud-gateway.update-route\n      with:\n        id: tools.routeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-route\n      description: Remove a gateway route, stopping traffic forwarding for matching requests\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: spring-cloud-gateway.delete-route\n      with:\n        id: tools.routeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sync-route-config\n      description: Synchronize the gateway route cache with the current configuration source\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: spring-cloud-gateway.refresh-routes\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: audit-global-filters\n      description: Audit all global filters applied to every request, including their execution order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-cloud-gateway.list-global-filters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-filter-options\n      description: Discover all available GatewayFilter factory options for configuring request/response transformation\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-cloud-gateway.list-route-filter-factories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-predicate-options\n      description: Discover all available RoutePredicateFactory options for defining traffic routing rules\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spring-cloud-gateway.list-predicate-factories\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-cloud-gateway/refs/heads/main/capabilities/api-gateway-management.yaml
tags:
- Spring Cloud
- API Gateway
- Route Management
- Platform Engineering
- Microservices
- DevOps
tools:
- description: Inspect all currently configured gateway routes including predicates, filters, URIs, ordering, and metadata
  hints:
    openWorld: false
    readOnly: true
  name: inspect-all-routes
- description: Inspect a specific gateway route definition by ID
  hints:
    openWorld: false
    readOnly: true
  name: inspect-route
- description: Deploy a new gateway route with Path/Host/Method predicates and filters such as StripPrefix, AddRequestHeader, CircuitBreaker, RequestRateLimiter
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-route
- description: Modify an existing gateway route's destination URI, matching predicates, or applied filters without downtime
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: modify-route
- description: Remove a gateway route, stopping traffic forwarding for matching requests
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-route
- description: Synchronize the gateway route cache with the current configuration source
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sync-route-config
- description: Audit all global filters applied to every request, including their execution order
  hints:
    openWorld: false
    readOnly: true
  name: audit-global-filters
- description: Discover all available GatewayFilter factory options for configuring request/response transformation
  hints:
    openWorld: false
    readOnly: true
  name: discover-filter-options
- description: Discover all available RoutePredicateFactory options for defining traffic routing rules
  hints:
    openWorld: false
    readOnly: true
  name: discover-predicate-options
---
