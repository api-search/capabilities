---
categories: []
consumed_apis: []
description: Unified capability for managing a Spring Cloud microservice platform including API gateway routing, service discovery inspection, and circuit breaker monitoring. Designed for platform engineers and DevOps teams.
layout: capability
name: Spring Cloud Microservice Platform
operations:
- description: List all configured gateway routes
  method: GET
  name: list-gateway-routes
  path: /v1/gateway/routes
- description: Create a new gateway route
  method: POST
  name: create-gateway-route
  path: /v1/gateway/routes
- description: Get route by ID
  method: GET
  name: get-gateway-route
  path: /v1/gateway/routes/{id}
- description: Delete a gateway route
  method: DELETE
  name: delete-gateway-route
  path: /v1/gateway/routes/{id}
- description: Refresh route cache
  method: POST
  name: refresh-gateway
  path: /v1/gateway/refresh
personas: []
provider_name: Spring Cloud
provider_slug: spring-cloud
search_terms:
- devops
- individual gateway route operations
- deploy gateway route
- distributed systems
- list all configured gateway routes
- list gateway routes
- create a new gateway route
- cloud native
- java
- refresh gateway
- force synchronization of the gateway route cache with current configuration
- inspect gateway routes
- deploy a new route to the spring cloud gateway for routing traffic to a microservice
- remove a gateway route, stopping traffic routing to that service
- api gateway
- circuit breaker
- service discovery
- get route by id
- inspect all spring cloud gateway routes to understand current traffic routing configuration
- get details of a specific gateway route by id including predicates, filters, and destination uri
- delete a gateway route
- get gateway route
- delete gateway route
- spring cloud
- refresh route cache
- remove gateway route
- gateway cache management
- create gateway route
- microservices
- spring framework
- sync gateway config
- api gateway route management
- platform engineering
slug: microservice-platform
source_filename: microservice-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spring Cloud Microservice Platform\n  description: Unified capability for managing a Spring Cloud microservice platform including API gateway routing, service\n    discovery inspection, and circuit breaker monitoring. Designed for platform engineers and DevOps teams.\n  tags:\n  - Spring Cloud\n  - Microservices\n  - Platform Engineering\n  - API Gateway\n  - Service Discovery\n  - DevOps\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPRING_GATEWAY_BASE_URL: SPRING_GATEWAY_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: gateway\n    baseUri: '{{SPRING_GATEWAY_BASE_URL}}/actuator/gateway'\n    description: Spring Cloud Gateway Actuator for runtime route management\n    resources:\n    - name: routes\n      path: /routes\n      description: Gateway route definitions\n      operations:\n      - name: list-routes\n        method: GET\n        description: List all configured gateway\
  \ routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-route\n        method: POST\n        description: Create a new gateway route\n        body:\n          type: json\n          data:\n            id: '{{tools.routeId}}'\n            uri: '{{tools.uri}}'\n            predicates: '{{tools.predicates}}'\n            filters: '{{tools.filters}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-route\n        method: GET\n        description: Get route by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Route identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-route\n        method: DELETE\n \
  \       description: Delete a gateway route\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Route identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refresh-routes\n        method: POST\n        description: Refresh the routes cache\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microservice-platform-api\n    description: Unified REST API for Spring Cloud microservice platform management.\n    resources:\n    - path: /v1/gateway/routes\n      name: gateway-routes\n      description: API gateway route management\n      operations:\n      - method: GET\n        name: list-gateway-routes\n        description: List all configured gateway routes\n        call: gateway.list-routes\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-gateway-route\n        description: Create a new gateway route\n        call: gateway.create-route\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gateway/routes/{id}\n      name: gateway-route-detail\n      description: Individual gateway route operations\n      operations:\n      - method: GET\n        name: get-gateway-route\n        description: Get route by ID\n        call: gateway.get-route\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-gateway-route\n        description: Delete a gateway route\n        call: gateway.delete-route\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gateway/refresh\n      name: gateway-refresh\n      description:\
  \ Gateway cache management\n      operations:\n      - method: POST\n        name: refresh-gateway\n        description: Refresh route cache\n        call: gateway.refresh-routes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: microservice-platform-mcp\n    transport: http\n    description: MCP server for AI-assisted Spring Cloud microservice platform management.\n    tools:\n    - name: inspect-gateway-routes\n      description: Inspect all Spring Cloud Gateway routes to understand current traffic routing configuration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: gateway.list-routes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-gateway-route\n      description: Get details of a specific gateway route by ID including predicates, filters, and destination URI\n      hints:\n        readOnly: true\n        openWorld: false\n      call: gateway.get-route\n\
  \      with:\n        id: tools.routeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deploy-gateway-route\n      description: Deploy a new route to the Spring Cloud Gateway for routing traffic to a microservice\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: gateway.create-route\n      with:\n        routeId: tools.routeId\n        uri: tools.destinationUri\n        predicates: tools.predicates\n        filters: tools.filters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-gateway-route\n      description: Remove a gateway route, stopping traffic routing to that service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: gateway.delete-route\n      with:\n        id: tools.routeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sync-gateway-config\n      description: Force\
  \ synchronization of the gateway route cache with current configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: gateway.refresh-routes\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spring-cloud/refs/heads/main/capabilities/microservice-platform.yaml
tags:
- Spring Cloud
- Microservices
- Platform Engineering
- API Gateway
- Service Discovery
- DevOps
tools:
- description: Inspect all Spring Cloud Gateway routes to understand current traffic routing configuration
  hints:
    openWorld: false
    readOnly: true
  name: inspect-gateway-routes
- description: Get details of a specific gateway route by ID including predicates, filters, and destination URI
  hints:
    openWorld: false
    readOnly: true
  name: get-gateway-route
- description: Deploy a new route to the Spring Cloud Gateway for routing traffic to a microservice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deploy-gateway-route
- description: Remove a gateway route, stopping traffic routing to that service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-gateway-route
- description: Force synchronization of the gateway route cache with current configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sync-gateway-config
---
