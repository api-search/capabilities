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
- list consumers
- update an existing apisix route.
- route, upstream, consumer, and ssl management workflow.
- list all gateway routes.
- lua
- create a backend upstream.
- list api consumers.
- kubernetes
- API Gateway Administrator
- list backend upstreams.
- create a new apisix route for traffic routing.
- traffic management
- create route
- create a new gateway route.
- delete route
- apache
- list all apisix gateway routes.
- update route
- create consumer
- api gateway
- engineers deploying and managing api gateway infrastructure.
- administrators configuring routes, consumers, and security policies.
- create an api consumer.
- Platform Engineer
- configuration
- list upstreams
- list all backend upstream configurations.
- authentication
- create a new api consumer with authentication plugins.
- cloud native
- open source
- delete an apisix route.
- nginx
- create upstream
- list all api consumers and their plugin configs.
- create a new backend upstream with load balancing config.
- list routes
- apache apisix
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
