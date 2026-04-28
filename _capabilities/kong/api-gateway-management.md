---
categories:
- api-management
consumed_apis:
- kong-admin
description: API gateway management workflow for platform engineers to configure services, routes, plugins, consumers, upstreams, and TLS certificates on Kong Gateway instances.
layout: capability
name: Kong API Gateway Management
operations:
- description: Retrieve gateway node info.
  method: GET
  name: get-node-info
  path: /v1/info
- description: List all services.
  method: GET
  name: list-services
  path: /v1/services
- description: Create a new service.
  method: POST
  name: create-service
  path: /v1/services
- description: List all routes.
  method: GET
  name: list-routes
  path: /v1/routes
- description: Create a new route.
  method: POST
  name: create-route
  path: /v1/routes
- description: List all consumers.
  method: GET
  name: list-consumers
  path: /v1/consumers
- description: List all plugins.
  method: GET
  name: list-plugins
  path: /v1/plugins
personas: []
provider_name: Kong
provider_slug: kong
search_terms:
- create route
- delete a service.
- list all routes.
- delete route
- upstream service management.
- api gateway
- update a route.
- get consumer
- retrieve a specific service.
- list plugins
- retrieve a specific plugin configuration.
- create a new service.
- create upstream
- get node status
- plugin management.
- list consumers
- list all plugins.
- update service
- get route
- delete plugin
- delete a route.
- list all configured upstream services.
- delete an upstream.
- get service
- create consumer
- list routes
- update route
- retrieve kong gateway node status.
- delete a consumer.
- get node info
- create a new route.
- retrieve kong gateway node information.
- list all tls certificates.
- create plugin
- create a new plugin configuration.
- list all tags and tagged entities.
- get plugin
- lua
- nginx
- route management.
- list all configured routes.
- retrieve a specific route.
- create a new upstream for load balancing.
- create a new route for a service.
- delete upstream
- list tags
- api consumer management.
- update a service configuration.
- list upstreams
- list all upstream load balancers.
- retrieve a specific consumer.
- list services
- open source
- list all enabled plugin names on the node.
- list all api consumers.
- list all consumers.
- create a new api consumer.
- list all services.
- delete consumer
- gateway node information.
- list all configured plugins.
- delete service
- delete a plugin.
- list enabled plugins
- configuration
- kong
- create service
- retrieve gateway node info.
- list certificates
- create a new upstream service.
slug: api-gateway-management
tags:
- Kong
- API Gateway
- Configuration
tools:
- description: Retrieve Kong Gateway node information.
  hints:
    readOnly: true
  name: get-node-info
- description: Retrieve Kong Gateway node status.
  hints:
    readOnly: true
  name: get-node-status
- description: List all configured upstream services.
  hints:
    readOnly: true
  name: list-services
- description: Create a new upstream service.
  hints:
    readOnly: false
  name: create-service
- description: Retrieve a specific service.
  hints:
    readOnly: true
  name: get-service
- description: Update a service configuration.
  hints:
    idempotent: true
    readOnly: false
  name: update-service
- description: Delete a service.
  hints:
    destructive: true
  name: delete-service
- description: List all configured routes.
  hints:
    readOnly: true
  name: list-routes
- description: Create a new route for a service.
  hints:
    readOnly: false
  name: create-route
- description: Retrieve a specific route.
  hints:
    readOnly: true
  name: get-route
- description: Update a route.
  hints:
    idempotent: true
    readOnly: false
  name: update-route
- description: Delete a route.
  hints:
    destructive: true
  name: delete-route
- description: List all API consumers.
  hints:
    readOnly: true
  name: list-consumers
- description: Create a new API consumer.
  hints:
    readOnly: false
  name: create-consumer
- description: Retrieve a specific consumer.
  hints:
    readOnly: true
  name: get-consumer
- description: Delete a consumer.
  hints:
    destructive: true
  name: delete-consumer
- description: List all configured plugins.
  hints:
    readOnly: true
  name: list-plugins
- description: Create a new plugin configuration.
  hints:
    readOnly: false
  name: create-plugin
- description: Retrieve a specific plugin configuration.
  hints:
    readOnly: true
  name: get-plugin
- description: Delete a plugin.
  hints:
    destructive: true
  name: delete-plugin
- description: List all enabled plugin names on the node.
  hints:
    readOnly: true
  name: list-enabled-plugins
- description: List all upstream load balancers.
  hints:
    readOnly: true
  name: list-upstreams
- description: Create a new upstream for load balancing.
  hints:
    readOnly: false
  name: create-upstream
- description: Delete an upstream.
  hints:
    destructive: true
  name: delete-upstream
- description: List all TLS certificates.
  hints:
    readOnly: true
  name: list-certificates
- description: List all tags and tagged entities.
  hints:
    readOnly: true
  name: list-tags
---
