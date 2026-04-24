---
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
- delete a route.
- list certificates
- create a new api consumer.
- list all tls certificates.
- update a route.
- create a new route.
- list all api consumers.
- delete a consumer.
- list all configured plugins.
- get node status
- delete route
- update service
- retrieve a specific service.
- list all configured routes.
- list all consumers.
- list all tags and tagged entities.
- list upstreams
- upstream service management.
- configuration
- api consumer management.
- delete plugin
- delete an upstream.
- retrieve kong gateway node information.
- get route
- list plugins
- list enabled plugins
- get consumer
- delete a plugin.
- retrieve kong gateway node status.
- nginx
- plugin management.
- create consumer
- list tags
- list all plugins.
- open source
- retrieve a specific plugin configuration.
- create plugin
- create route
- update route
- delete consumer
- list all enabled plugin names on the node.
- create a new plugin configuration.
- gateway node information.
- delete service
- create a new upstream for load balancing.
- get plugin
- create a new route for a service.
- lua
- api gateway
- retrieve gateway node info.
- create a new service.
- create service
- list all routes.
- get node info
- list consumers
- get service
- update a service configuration.
- list services
- retrieve a specific consumer.
- delete a service.
- list all upstream load balancers.
- list routes
- list all configured upstream services.
- list all services.
- retrieve a specific route.
- route management.
- delete upstream
- kong
- create upstream
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
