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
- create route
- API Gateway Administrator
- route, upstream, consumer, and ssl management workflow.
- delete route
- api gateway
- delete an apisix route.
- kubernetes
- create upstream
- create a new gateway route.
- list consumers
- create an api consumer.
- authentication
- administrators configuring routes, consumers, and security policies.
- create consumer
- list routes
- list all gateway routes.
- update route
- create a new backend upstream with load balancing config.
- list all apisix gateway routes.
- traffic management
- engineers deploying and managing api gateway infrastructure.
- list api consumers.
- apache apisix
- lua
- create a new apisix route for traffic routing.
- nginx
- update an existing apisix route.
- create a new api consumer with authentication plugins.
- Platform Engineer
- apache
- list all backend upstream configurations.
- list upstreams
- create a backend upstream.
- list backend upstreams.
- open source
- list all api consumers and their plugin configs.
- configuration
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
