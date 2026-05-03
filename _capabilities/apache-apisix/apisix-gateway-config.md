---
categories:
- api-management
consumed_apis:
- apisix-admin
description: Unified capability for configuring and managing Apache APISIX API gateway resources including routes, upstreams, services, consumers, and SSL certificates. Used by platform engineers and API gateway administrators.
layout: capability
name: Apache APISIX Gateway Configuration
operations:
- description: List all gateway routes.
  method: GET
  name: list-routes
  path: /v1/routes
- description: Create a new gateway route.
  method: POST
  name: create-route
  path: /v1/routes
- description: List backend upstreams.
  method: GET
  name: list-upstreams
  path: /v1/upstreams
- description: Create a backend upstream.
  method: POST
  name: create-upstream
  path: /v1/upstreams
- description: List API consumers.
  method: GET
  name: list-consumers
  path: /v1/consumers
- description: Create an API consumer.
  method: POST
  name: create-consumer
  path: /v1/consumers
personas: []
provider_name: Apache APISIX
provider_slug: apache-apisix
search_terms:
- list all apisix gateway routes.
- update route
- Platform Engineer
- create a new api consumer with authentication plugins.
- lua
- delete route
- engineers deploying and managing api gateway infrastructure.
- open source
- update an existing apisix route.
- create route
- create consumer
- cloud native
- create a new gateway route.
- traffic management
- create upstream
- nginx
- authentication
- list all api consumers and their plugin configs.
- kubernetes
- list backend upstreams.
- create a new backend upstream with load balancing config.
- route, upstream, consumer, and ssl management workflow.
- list routes
- configuration
- API Gateway Administrator
- list consumers
- api gateway
- create an api consumer.
- list upstreams
- delete an apisix route.
- administrators configuring routes, consumers, and security policies.
- apache
- create a new apisix route for traffic routing.
- list all backend upstream configurations.
- list all gateway routes.
- create a backend upstream.
- apache apisix
- list api consumers.
slug: apisix-gateway-config
source_filename: apisix-gateway-config.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Apache APISIX Gateway Configuration\n  description: Unified capability for configuring and managing Apache APISIX API\n    gateway resources including routes, upstreams, services, consumers, and SSL \n    certificates. Used by platform engineers and API gateway administrators.\n  tags:\n  - Apache APISIX\n  - API Gateway\n  - Configuration\n  - Cloud Native\n  - Traffic Management\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    APISIX_ADMIN_KEY: APISIX_ADMIN_KEY\ncapability:\n  consumes:\n  - import: apisix-admin\n    location: ./shared/apisix-admin.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apisix-gateway-api\n    description: Unified REST API for APISIX gateway configuration.\n    resources:\n    - path: /v1/routes\n      name: routes\n      operations:\n      - method: GET\n        name: list-routes\n        description: List all gateway routes.\n        call: apisix-admin.list-routes\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-route\n        description: Create a new gateway route.\n        call: apisix-admin.create-route\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/upstreams\n      name: upstreams\n      operations:\n      - method: GET\n        name: list-upstreams\n        description: List backend upstreams.\n        call: apisix-admin.list-upstreams\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-upstream\n        description: Create a backend upstream.\n        call: apisix-admin.create-upstream\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/consumers\n      name: consumers\n      operations:\n      - method: GET\n        name: list-consumers\n        description: List API consumers.\n        call: apisix-admin.list-consumers\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-consumer\n        description: Create an API consumer.\n        call: apisix-admin.create-consumer\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apisix-gateway-mcp\n    transport: http\n    description: MCP server for AI-assisted APISIX gateway configuration.\n    tools:\n    - name: list-routes\n      description: List all APISIX gateway routes.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: apisix-admin.list-routes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-route\n      description: Create a new APISIX route for traffic routing.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: apisix-admin.create-route\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-route\n\
  \      description: Update an existing APISIX route.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: apisix-admin.update-route\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-route\n      description: Delete an APISIX route.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: apisix-admin.delete-route\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-upstreams\n      description: List all backend upstream configurations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: apisix-admin.list-upstreams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-upstream\n      description: Create a new backend upstream with load balancing config.\n      hints:\n        readOnly: false\n        openWorld: false\n\
  \      call: apisix-admin.create-upstream\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-consumers\n      description: List all API consumers and their plugin configs.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: apisix-admin.list-consumers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-consumer\n      description: Create a new API consumer with authentication plugins.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: apisix-admin.create-consumer\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-apisix/refs/heads/main/capabilities/apisix-gateway-config.yaml
tags:
- Apache APISIX
- API Gateway
- Configuration
- Cloud Native
- Traffic Management
tools:
- description: List all APISIX gateway routes.
  hints:
    openWorld: true
    readOnly: true
  name: list-routes
- description: Create a new APISIX route for traffic routing.
  hints:
    openWorld: false
    readOnly: false
  name: create-route
- description: Update an existing APISIX route.
  hints:
    idempotent: true
    readOnly: false
  name: update-route
- description: Delete an APISIX route.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-route
- description: List all backend upstream configurations.
  hints:
    openWorld: true
    readOnly: true
  name: list-upstreams
- description: Create a new backend upstream with load balancing config.
  hints:
    openWorld: false
    readOnly: false
  name: create-upstream
- description: List all API consumers and their plugin configs.
  hints:
    openWorld: true
    readOnly: true
  name: list-consumers
- description: Create a new API consumer with authentication plugins.
  hints:
    openWorld: false
    readOnly: false
  name: create-consumer
---
