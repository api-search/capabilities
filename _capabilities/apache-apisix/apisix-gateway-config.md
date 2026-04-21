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
- cloud native
- create consumer
- configuration
- kubernetes
- update an existing apisix route.
- open source
- Platform Engineer
- nginx
- delete route
- list api consumers.
- list consumers
- api gateway
- apache
- create a new api consumer with authentication plugins.
- update route
- authentication
- list backend upstreams.
- create upstream
- apache apisix
- create a new gateway route.
- list routes
- list all api consumers and their plugin configs.
- list all apisix gateway routes.
- administrators configuring routes, consumers, and security policies.
- list all backend upstream configurations.
- traffic management
- engineers deploying and managing api gateway infrastructure.
- delete an apisix route.
- lua
- create a new apisix route for traffic routing.
- API Gateway Administrator
- create a new backend upstream with load balancing config.
- list upstreams
- list all gateway routes.
- create a backend upstream.
- create an api consumer.
- route, upstream, consumer, and ssl management workflow.
- create route
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
