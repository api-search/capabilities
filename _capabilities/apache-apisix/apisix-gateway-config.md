---
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
- create a new apisix route for traffic routing.
- configuration
- administrators configuring routes, consumers, and security policies.
- list upstreams
- list backend upstreams.
- authentication
- create a new gateway route.
- update an existing apisix route.
- list routes
- apache
- create route
- list all api consumers and their plugin configs.
- create consumer
- API Gateway Administrator
- kubernetes
- list consumers
- update route
- api gateway
- delete route
- route, upstream, consumer, and ssl management workflow.
- list all gateway routes.
- create upstream
- create a backend upstream.
- list all backend upstream configurations.
- list api consumers.
- create a new api consumer with authentication plugins.
- Platform Engineer
- nginx
- traffic management
- list all apisix gateway routes.
- create an api consumer.
- apache apisix
- lua
- delete an apisix route.
- engineers deploying and managing api gateway infrastructure.
- create a new backend upstream with load balancing config.
- open source
- cloud native
slug: apisix-gateway-config
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
