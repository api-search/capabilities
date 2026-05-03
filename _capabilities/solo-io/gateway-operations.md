---
categories: []
consumed_apis:
- gloo-gateway
- gloo-portal
description: Unified capability for operating Solo.io Gloo Gateway deployments. Combines the Gateway Management API for control plane administration (upstreams, virtual services, route tables, proxies, gateways) with the Portal Server API for developer portal management (API keys, usage plans). Used by platform engineers, API operators, and developer portal administrators.
layout: capability
name: Solo.io Gateway Operations
operations:
- description: List all upstream backend services
  method: GET
  name: list-upstreams
  path: /v1/upstreams
- description: Get upstream details
  method: GET
  name: get-upstream
  path: /v1/upstreams/{namespace}/{name}
- description: List all virtual services
  method: GET
  name: list-virtual-services
  path: /v1/virtual-services
- description: Get virtual service details
  method: GET
  name: get-virtual-service
  path: /v1/virtual-services/{namespace}/{name}
- description: List all route tables
  method: GET
  name: list-route-tables
  path: /v1/route-tables
- description: List all proxies
  method: GET
  name: list-proxies
  path: /v1/proxies
- description: List all gateways
  method: GET
  name: list-gateways
  path: /v1/gateways
- description: Check control plane health
  method: GET
  name: health-check
  path: /v1/health
- description: List APIs in developer portal
  method: GET
  name: list-portal-apis
  path: /v1/portal/apis
- description: List usage plans
  method: GET
  name: list-usage-plans
  path: /v1/portal/usage-plans
- description: List API keys
  method: GET
  name: list-api-keys
  path: /v1/portal/api-keys
- description: Create API key
  method: POST
  name: create-api-key
  path: /v1/portal/api-keys
personas: []
provider_name: Solo.io
provider_slug: solo-io
search_terms:
- list usage plans
- automation
- list api keys
- resiliency
- get virtual service
- check control plane health
- management
- solo.io
- security
- get portal api schema
- list all upstream backend services registered with gloo gateway, optionally filtered by namespace
- envoy proxy
- list gateways
- get details of a specific upstream service including health checks and tls config
- list all gateway resources defining listener addresses, ports, and tls
- check health status of gloo gateway control plane and its components
- compiled envoy proxy configurations
- analytics
- retrieve the openapi or graphql schema for a portal api
- delegated route table management
- list compiled envoy proxy configurations generated from gateway resources
- control plane health
- cloud native
- list route tables used for delegated routing configuration across teams
- traffic management
- api management
- list all upstream backend services
- get gateway
- ai gateway
- developer portal api catalog
- list all virtual services
- get details of a specific portal api including schema and usage plans
- permanently delete an api key, revoking access to the associated api product
- list all gateways
- list apis in developer portal
- list all route tables
- developer portal usage plans
- get route table
- list virtual services
- gateways
- api gateway
- service mesh
- gateway listener management
- health check
- create api key
- list upstreams
- individual upstream details
- get upstream
- list all virtual services with domains, routing rules, and security policies
- get compiled proxy configuration with all listeners, routes, and clusters
- individual virtual service configuration
- list route tables
- traffic control
- list all apis published in the gloo developer portal
- get gateway listener configuration including tls settings and virtual service bindings
- get full virtual service configuration including routes, rate limiting, and authentication
- observability
- get route table with all routes, matchers, and upstream destinations
- developer portal
- delete api key
- gateway health check
- backend upstream service management
- get upstream details
- list proxies
- get proxy
- get portal api
- list api keys for the authenticated portal user
- platform
- list available usage plans with rate limits and api product access
- create a new api key for accessing an api product under a usage plan
- list portal apis
- monetization
- list all proxies
- get virtual service details
- developer api key management
- virtual service routing rules
slug: gateway-operations
source_filename: gateway-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Solo.io Gateway Operations\"\n  description: >-\n    Unified capability for operating Solo.io Gloo Gateway deployments. Combines\n    the Gateway Management API for control plane administration (upstreams, virtual\n    services, route tables, proxies, gateways) with the Portal Server API for\n    developer portal management (API keys, usage plans). Used by platform\n    engineers, API operators, and developer portal administrators.\n  tags:\n    - API Gateway\n    - API Management\n    - Cloud Native\n    - Developer Portal\n    - Envoy Proxy\n    - Solo.io\n    - Traffic Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      GLOO_GATEWAY_BEARER_TOKEN: GLOO_GATEWAY_BEARER_TOKEN\n      GLOO_PORTAL_BEARER_TOKEN: GLOO_PORTAL_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: gloo-gateway\n      location: ./shared/gloo-gateway-management.yaml\n    - import: gloo-portal\n\
  \      location: ./shared/gloo-portal.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: solo-io-gateway-ops-api\n      description: \"Unified REST API for Solo.io Gloo Gateway platform operations.\"\n      resources:\n        - path: /v1/upstreams\n          name: upstreams\n          description: \"Backend upstream service management\"\n          operations:\n            - method: GET\n              name: list-upstreams\n              description: \"List all upstream backend services\"\n              call: \"gloo-gateway.list-upstreams\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/upstreams/{namespace}/{name}\n          name: upstream-detail\n          description: \"Individual upstream details\"\n          operations:\n            - method: GET\n              name: get-upstream\n              description: \"Get upstream\
  \ details\"\n              call: \"gloo-gateway.get-upstream\"\n              with:\n                namespace: \"rest.namespace\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/virtual-services\n          name: virtual-services\n          description: \"Virtual service routing rules\"\n          operations:\n            - method: GET\n              name: list-virtual-services\n              description: \"List all virtual services\"\n              call: \"gloo-gateway.list-virtual-services\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/virtual-services/{namespace}/{name}\n          name: virtual-service-detail\n          description: \"Individual virtual service configuration\"\n          operations:\n            - method: GET\n \
  \             name: get-virtual-service\n              description: \"Get virtual service details\"\n              call: \"gloo-gateway.get-virtual-service\"\n              with:\n                namespace: \"rest.namespace\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/route-tables\n          name: route-tables\n          description: \"Delegated route table management\"\n          operations:\n            - method: GET\n              name: list-route-tables\n              description: \"List all route tables\"\n              call: \"gloo-gateway.list-route-tables\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/proxies\n          name: proxies\n          description: \"Compiled Envoy proxy configurations\"\n          operations:\n\
  \            - method: GET\n              name: list-proxies\n              description: \"List all proxies\"\n              call: \"gloo-gateway.list-proxies\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/gateways\n          name: gateways\n          description: \"Gateway listener management\"\n          operations:\n            - method: GET\n              name: list-gateways\n              description: \"List all gateways\"\n              call: \"gloo-gateway.list-gateways\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/health\n          name: health\n          description: \"Control plane health\"\n          operations:\n            - method: GET\n              name: health-check\n             \
  \ description: \"Check control plane health\"\n              call: \"gloo-gateway.health-check\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portal/apis\n          name: portal-apis\n          description: \"Developer portal API catalog\"\n          operations:\n            - method: GET\n              name: list-portal-apis\n              description: \"List APIs in developer portal\"\n              call: \"gloo-portal.list-apis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/portal/usage-plans\n          name: portal-usage-plans\n          description: \"Developer portal usage plans\"\n          operations:\n            - method: GET\n              name: list-usage-plans\n              description: \"List usage plans\"\n              call: \"gloo-portal.list-usage-plans\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/portal/api-keys\n          name: portal-api-keys\n          description: \"Developer API key management\"\n          operations:\n            - method: GET\n              name: list-api-keys\n              description: \"List API keys\"\n              call: \"gloo-portal.list-api-keys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api-key\n              description: \"Create API key\"\n              call: \"gloo-portal.create-api-key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: solo-io-gateway-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Solo.io Gloo Gateway platform operations.\"\n      tools:\n        - name: list-upstreams\n          description: \"List all upstream backend\
  \ services registered with Gloo Gateway, optionally filtered by namespace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gloo-gateway.list-upstreams\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-upstream\n          description: \"Get details of a specific upstream service including health checks and TLS config\"\n          hints:\n            readOnly: true\n          call: \"gloo-gateway.get-upstream\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-virtual-services\n          description: \"List all virtual services with domains, routing rules, and security policies\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"gloo-gateway.list-virtual-services\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-virtual-service\n          description: \"Get full virtual service configuration including routes, rate limiting, and authentication\"\n          hints:\n            readOnly: true\n          call: \"gloo-gateway.get-virtual-service\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-route-tables\n          description: \"List route tables used for delegated routing configuration across teams\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gloo-gateway.list-route-tables\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n\n        - name: get-route-table\n          description: \"Get route table with all routes, matchers, and upstream destinations\"\n          hints:\n            readOnly: true\n          call: \"gloo-gateway.get-route-table\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-proxies\n          description: \"List compiled Envoy proxy configurations generated from gateway resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gloo-gateway.list-proxies\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-proxy\n          description: \"Get compiled proxy configuration with all listeners, routes, and clusters\"\n     \
  \     hints:\n            readOnly: true\n          call: \"gloo-gateway.get-proxy\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-gateways\n          description: \"List all gateway resources defining listener addresses, ports, and TLS\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gloo-gateway.list-gateways\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-gateway\n          description: \"Get gateway listener configuration including TLS settings and virtual service bindings\"\n          hints:\n            readOnly: true\n          call: \"gloo-gateway.get-gateway\"\n          with:\n            namespace: \"tools.namespace\"\n            name: \"tools.name\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: gateway-health-check\n          description: \"Check health status of Gloo Gateway control plane and its components\"\n          hints:\n            readOnly: true\n          call: \"gloo-gateway.health-check\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-portal-apis\n          description: \"List all APIs published in the Gloo developer portal\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gloo-portal.list-apis\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-portal-api\n          description: \"Get details of a specific portal API including schema and usage plans\"\n          hints:\n            readOnly: true\n\
  \          call: \"gloo-portal.get-api\"\n          with:\n            apiId: \"tools.apiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-portal-api-schema\n          description: \"Retrieve the OpenAPI or GraphQL schema for a portal API\"\n          hints:\n            readOnly: true\n          call: \"gloo-portal.get-api-schema\"\n          with:\n            apiId: \"tools.apiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-usage-plans\n          description: \"List available usage plans with rate limits and API product access\"\n          hints:\n            readOnly: true\n          call: \"gloo-portal.list-usage-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-api-keys\n          description: \"List API keys for the authenticated portal user\"\n          hints:\n            readOnly:\
  \ true\n          call: \"gloo-portal.list-api-keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-api-key\n          description: \"Create a new API key for accessing an API product under a usage plan\"\n          hints:\n            readOnly: false\n          call: \"gloo-portal.create-api-key\"\n          with:\n            name: \"tools.name\"\n            usagePlanId: \"tools.usagePlanId\"\n            apiProductId: \"tools.apiProductId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-api-key\n          description: \"Permanently delete an API key, revoking access to the associated API product\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"gloo-portal.delete-api-key\"\n          with:\n            apiKeyId: \"tools.apiKeyId\"\n          outputParameters:\n          \
  \  - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/solo-io/refs/heads/main/capabilities/gateway-operations.yaml
tags:
- API Gateway
- API Management
- Cloud Native
- Developer Portal
- Envoy Proxy
- Solo.io
- Traffic Management
tools:
- description: List all upstream backend services registered with Gloo Gateway, optionally filtered by namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-upstreams
- description: Get details of a specific upstream service including health checks and TLS config
  hints:
    readOnly: true
  name: get-upstream
- description: List all virtual services with domains, routing rules, and security policies
  hints:
    openWorld: true
    readOnly: true
  name: list-virtual-services
- description: Get full virtual service configuration including routes, rate limiting, and authentication
  hints:
    readOnly: true
  name: get-virtual-service
- description: List route tables used for delegated routing configuration across teams
  hints:
    openWorld: true
    readOnly: true
  name: list-route-tables
- description: Get route table with all routes, matchers, and upstream destinations
  hints:
    readOnly: true
  name: get-route-table
- description: List compiled Envoy proxy configurations generated from gateway resources
  hints:
    openWorld: true
    readOnly: true
  name: list-proxies
- description: Get compiled proxy configuration with all listeners, routes, and clusters
  hints:
    readOnly: true
  name: get-proxy
- description: List all gateway resources defining listener addresses, ports, and TLS
  hints:
    openWorld: true
    readOnly: true
  name: list-gateways
- description: Get gateway listener configuration including TLS settings and virtual service bindings
  hints:
    readOnly: true
  name: get-gateway
- description: Check health status of Gloo Gateway control plane and its components
  hints:
    readOnly: true
  name: gateway-health-check
- description: List all APIs published in the Gloo developer portal
  hints:
    openWorld: true
    readOnly: true
  name: list-portal-apis
- description: Get details of a specific portal API including schema and usage plans
  hints:
    readOnly: true
  name: get-portal-api
- description: Retrieve the OpenAPI or GraphQL schema for a portal API
  hints:
    readOnly: true
  name: get-portal-api-schema
- description: List available usage plans with rate limits and API product access
  hints:
    readOnly: true
  name: list-usage-plans
- description: List API keys for the authenticated portal user
  hints:
    readOnly: true
  name: list-api-keys
- description: Create a new API key for accessing an API product under a usage plan
  hints:
    readOnly: false
  name: create-api-key
- description: Permanently delete an API key, revoking access to the associated API product
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-key
---
