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
- API Gateway Administrator
- create a backend upstream.
- create a new apisix route for traffic routing.
- update an existing apisix route.
- delete route
- list all backend upstream configurations.
- Platform Engineer
- apache apisix
- administrators configuring routes, consumers, and security policies.
- configuration
- list backend upstreams.
- list all apisix gateway routes.
- nginx
- list all api consumers and their plugin configs.
- apache
- create consumer
- authentication
- engineers deploying and managing api gateway infrastructure.
- open source
- create route
- update route
- traffic management
- list api consumers.
- list all gateway routes.
- create a new backend upstream with load balancing config.
- api gateway
- route, upstream, consumer, and ssl management workflow.
- lua
- create a new api consumer with authentication plugins.
- list consumers
- create a new gateway route.
- cloud native
- create an api consumer.
- list routes
- delete an apisix route.
- kubernetes
- create upstream
- list upstreams
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
