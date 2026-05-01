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
- delete plugin
- create route
- update route
- api gateway
- list all routes.
- retrieve a specific service.
- retrieve kong gateway node status.
- get consumer
- delete an upstream.
- list tags
- list all services.
- retrieve a specific plugin configuration.
- delete service
- create a new upstream service.
- delete a plugin.
- api consumer management.
- list all tls certificates.
- lua
- nginx
- create plugin
- delete upstream
- gateway node information.
- update service
- create consumer
- retrieve kong gateway node information.
- list all configured routes.
- list routes
- list consumers
- list certificates
- retrieve a specific consumer.
- list all tags and tagged entities.
- create a new api consumer.
- get route
- list all configured upstream services.
- list all upstream load balancers.
- create upstream
- upstream service management.
- create service
- list all plugins.
- retrieve a specific route.
- kong
- delete route
- list services
- create a new service.
- create a new route.
- delete a consumer.
- create a new plugin configuration.
- get plugin
- list all enabled plugin names on the node.
- get service
- create a new route for a service.
- list all api consumers.
- plugin management.
- route management.
- delete consumer
- list all configured plugins.
- list enabled plugins
- configuration
- delete a service.
- create a new upstream for load balancing.
- list plugins
- open source
- update a service configuration.
- retrieve gateway node info.
- get node status
- list upstreams
- get node info
- delete a route.
- list all consumers.
- update a route.
slug: api-gateway-management
source_filename: api-gateway-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Kong API Gateway Management\"\n  description: \"API gateway management workflow for platform engineers to configure services, routes, plugins, consumers, upstreams, and TLS certificates on Kong Gateway instances.\"\n  tags:\n    - Kong\n    - API Gateway\n    - Configuration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      KONG_ADMIN_URL: KONG_ADMIN_URL\n\ncapability:\n  consumes:\n    - import: kong-admin\n      location: ./shared/kong-admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: api-gateway-management-api\n      description: \"Unified REST API for Kong Gateway management.\"\n      resources:\n        - path: /v1/info\n          name: info\n          description: \"Gateway node information.\"\n          operations:\n            - method: GET\n              name: get-node-info\n              description: \"Retrieve gateway node info.\"\n   \
  \           call: \"kong-admin.get-node-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/services\n          name: services\n          description: \"Upstream service management.\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List all services.\"\n              call: \"kong-admin.list-services\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-service\n              description: \"Create a new service.\"\n              call: \"kong-admin.create-service\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/routes\n          name: routes\n          description: \"Route management.\"\n          operations:\n            - method: GET\n              name: list-routes\n  \
  \            description: \"List all routes.\"\n              call: \"kong-admin.list-routes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-route\n              description: \"Create a new route.\"\n              call: \"kong-admin.create-route\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/consumers\n          name: consumers\n          description: \"API consumer management.\"\n          operations:\n            - method: GET\n              name: list-consumers\n              description: \"List all consumers.\"\n              call: \"kong-admin.list-consumers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/plugins\n          name: plugins\n          description: \"Plugin management.\"\n          operations:\n            - method:\
  \ GET\n              name: list-plugins\n              description: \"List all plugins.\"\n              call: \"kong-admin.list-plugins\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: api-gateway-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Kong Gateway management.\"\n      tools:\n        - name: get-node-info\n          description: \"Retrieve Kong Gateway node information.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.get-node-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-node-status\n          description: \"Retrieve Kong Gateway node status.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.get-node-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n       \
  \ - name: list-services\n          description: \"List all configured upstream services.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.list-services\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-service\n          description: \"Create a new upstream service.\"\n          hints:\n            readOnly: false\n          call: \"kong-admin.create-service\"\n          with:\n            name: \"tools.name\"\n            url: \"tools.url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-service\n          description: \"Retrieve a specific service.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.get-service\"\n          with:\n            service_id_or_name: \"tools.service_id_or_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-service\n\
  \          description: \"Update a service configuration.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"kong-admin.update-service\"\n          with:\n            service_id_or_name: \"tools.service_id_or_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-service\n          description: \"Delete a service.\"\n          hints:\n            destructive: true\n          call: \"kong-admin.delete-service\"\n          with:\n            service_id_or_name: \"tools.service_id_or_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-routes\n          description: \"List all configured routes.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.list-routes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-route\n          description:\
  \ \"Create a new route for a service.\"\n          hints:\n            readOnly: false\n          call: \"kong-admin.create-route\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-route\n          description: \"Retrieve a specific route.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.get-route\"\n          with:\n            route_id_or_name: \"tools.route_id_or_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-route\n          description: \"Update a route.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"kong-admin.update-route\"\n          with:\n            route_id_or_name: \"tools.route_id_or_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-route\n          description: \"Delete a route.\"\n          hints:\n\
  \            destructive: true\n          call: \"kong-admin.delete-route\"\n          with:\n            route_id_or_name: \"tools.route_id_or_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-consumers\n          description: \"List all API consumers.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.list-consumers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-consumer\n          description: \"Create a new API consumer.\"\n          hints:\n            readOnly: false\n          call: \"kong-admin.create-consumer\"\n          with:\n            username: \"tools.username\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-consumer\n          description: \"Retrieve a specific consumer.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.get-consumer\"\
  \n          with:\n            consumer_id_or_username: \"tools.consumer_id_or_username\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-consumer\n          description: \"Delete a consumer.\"\n          hints:\n            destructive: true\n          call: \"kong-admin.delete-consumer\"\n          with:\n            consumer_id_or_username: \"tools.consumer_id_or_username\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-plugins\n          description: \"List all configured plugins.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.list-plugins\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-plugin\n          description: \"Create a new plugin configuration.\"\n          hints:\n            readOnly: false\n          call: \"kong-admin.create-plugin\"\n          with:\n\
  \            name: \"tools.name\"\n            config: \"tools.config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-plugin\n          description: \"Retrieve a specific plugin configuration.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.get-plugin\"\n          with:\n            plugin_id: \"tools.plugin_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-plugin\n          description: \"Delete a plugin.\"\n          hints:\n            destructive: true\n          call: \"kong-admin.delete-plugin\"\n          with:\n            plugin_id: \"tools.plugin_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-enabled-plugins\n          description: \"List all enabled plugin names on the node.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.list-enabled-plugins\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-upstreams\n          description: \"List all upstream load balancers.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.list-upstreams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-upstream\n          description: \"Create a new upstream for load balancing.\"\n          hints:\n            readOnly: false\n          call: \"kong-admin.create-upstream\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-upstream\n          description: \"Delete an upstream.\"\n          hints:\n            destructive: true\n          call: \"kong-admin.delete-upstream\"\n          with:\n            upstream_id_or_name: \"tools.upstream_id_or_name\"\n          outputParameters:\n         \
  \   - type: object\n              mapping: \"$.\"\n        - name: list-certificates\n          description: \"List all TLS certificates.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.list-certificates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tags\n          description: \"List all tags and tagged entities.\"\n          hints:\n            readOnly: true\n          call: \"kong-admin.list-tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kong/refs/heads/main/capabilities/api-gateway-management.yaml
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
