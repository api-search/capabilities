---
categories: []
consumed_apis: []
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
- analytics
- list all apis published in the gloo developer portal
- list usage plans
- delete api key
- list proxies
- list all gateway resources defining listener addresses, ports, and tls
- automation
- ai gateway
- list apis in developer portal
- platform
- list compiled envoy proxy configurations generated from gateway resources
- solo.io
- get details of a specific upstream service including health checks and tls config
- cloud native
- gateways
- health check
- get details of a specific portal api including schema and usage plans
- service mesh
- api management
- developer portal usage plans
- list all route tables
- get portal api schema
- list api keys for the authenticated portal user
- get compiled proxy configuration with all listeners, routes, and clusters
- get route table
- list all gateways
- get upstream
- compiled envoy proxy configurations
- delegated route table management
- developer portal
- retrieve the openapi or graphql schema for a portal api
- list upstreams
- list all upstream backend services
- list virtual services
- permanently delete an api key, revoking access to the associated api product
- observability
- api gateway
- management
- check control plane health
- list all upstream backend services registered with gloo gateway, optionally filtered by namespace
- list available usage plans with rate limits and api product access
- get portal api
- get virtual service
- gateway listener management
- list api keys
- backend upstream service management
- traffic management
- list gateways
- control plane health
- get full virtual service configuration including routes, rate limiting, and authentication
- create a new api key for accessing an api product under a usage plan
- get gateway listener configuration including tls settings and virtual service bindings
- traffic control
- list all proxies
- virtual service routing rules
- get route table with all routes, matchers, and upstream destinations
- monetization
- developer api key management
- gateway health check
- list route tables used for delegated routing configuration across teams
- get proxy
- list portal apis
- list all virtual services with domains, routing rules, and security policies
- envoy proxy
- get upstream details
- list all virtual services
- individual upstream details
- get virtual service details
- individual virtual service configuration
- resiliency
- list route tables
- security
- developer portal api catalog
- check health status of gloo gateway control plane and its components
- get gateway
- create api key
slug: gateway-operations
source_filename: gateway-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Solo.io Gateway Operations\n  description: Unified capability for operating Solo.io Gloo Gateway deployments. Combines the Gateway Management API for\n    control plane administration (upstreams, virtual services, route tables, proxies, gateways) with the Portal Server API\n    for developer portal management (API keys, usage plans). Used by platform engineers, API operators, and developer portal\n    administrators.\n  tags:\n  - API Gateway\n  - API Management\n  - Cloud Native\n  - Developer Portal\n  - Envoy Proxy\n  - Solo.io\n  - Traffic Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GLOO_GATEWAY_BEARER_TOKEN: GLOO_GATEWAY_BEARER_TOKEN\n    GLOO_PORTAL_BEARER_TOKEN: GLOO_PORTAL_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: gloo-gateway\n    baseUri: https://gloo.example.com/api/v1\n    description: Gloo Gateway Management API for control plane administration\n\
  \    authentication:\n      type: bearer\n      token: '{{GLOO_GATEWAY_BEARER_TOKEN}}'\n    resources:\n    - name: upstreams\n      path: /upstreams\n      description: Backend upstream destination management\n      operations:\n      - name: list-upstreams\n        method: GET\n        description: List all upstream destinations registered with Gloo Gateway\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          required: false\n          description: Filter upstreams by namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-upstream\n        method: GET\n        description: Get detailed information about a specific upstream\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Kubernetes namespace of the upstream\n        - name: name\n  \
  \        in: path\n          type: string\n          required: true\n          description: Name of the upstream\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: virtual-services\n      path: /virtualservices\n      description: Virtual service routing and traffic management\n      operations:\n      - name: list-virtual-services\n        method: GET\n        description: List all virtual services with routing rules and policies\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          required: false\n          description: Filter virtual services by namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-virtual-service\n        method: GET\n        description: Get configuration of a specific virtual service\n        inputParameters:\n        -\
  \ name: namespace\n          in: path\n          type: string\n          required: true\n          description: Kubernetes namespace of the virtual service\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the virtual service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: route-tables\n      path: /routetables\n      description: Modular route table management\n      operations:\n      - name: list-route-tables\n        method: GET\n        description: List all route tables for delegated routing configuration\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          required: false\n          description: Filter route tables by namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: get-route-table\n        method: GET\n        description: Get configuration of a specific route table\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Kubernetes namespace of the route table\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the route table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: proxies\n      path: /proxies\n      description: Compiled Envoy proxy configuration management\n      operations:\n      - name: list-proxies\n        method: GET\n        description: List all proxy configurations managed by Gloo Gateway\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          required: false\n          description: Filter proxies by namespace\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-proxy\n        method: GET\n        description: Get the compiled proxy configuration including listeners and routes\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Kubernetes namespace of the proxy\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the proxy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gateways\n      path: /gateways\n      description: Gateway listener and ingress configuration\n      operations:\n      - name: list-gateways\n        method: GET\n        description: List all gateway resources with listener configurations\n        inputParameters:\n        - name:\
  \ namespace\n          in: query\n          type: string\n          required: false\n          description: Filter gateways by namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-gateway\n        method: GET\n        description: Get configuration of a specific gateway including TLS settings\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Kubernetes namespace of the gateway\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the gateway\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /check\n      description: Control plane health monitoring\n      operations:\n      - name: health-check\n        method: GET\n\
  \        description: Check health of Gloo Gateway control plane components\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: gloo-portal\n    baseUri: https://portal.example.com/v1\n    description: Gloo Portal Server API for developer portal management\n    authentication:\n      type: bearer\n      token: '{{GLOO_PORTAL_BEARER_TOKEN}}'\n    resources:\n    - name: users\n      path: /me\n      description: User profile and session management\n      operations:\n      - name: get-current-user\n        method: GET\n        description: Get the current authenticated user's profile and permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis\n      path: /apis\n      description: API product discovery and schema retrieval\n      operations:\n      - name: list-apis\n        method:\
  \ GET\n        description: List all APIs visible to the current user\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of APIs to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-api\n        method: GET\n        description: Get details of a specific API product\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-api-schema\n        method: GET\n        description: Get\
  \ the OpenAPI schema for a specific API product\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: usage-plans\n      path: /usage-plans\n      description: Usage plan discovery for rate limiting and quota management\n      operations:\n      - name: list-usage-plans\n        method: GET\n        description: List all usage plans available to the current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-keys\n      path: /api-keys\n      description: API key lifecycle management\n      operations:\n      - name: list-api-keys\n        method: GET\n        description: List all API keys for the current user\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-key\n        method: POST\n        description: Create a new API key for a usage plan and API product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            usagePlanId: '{{tools.usagePlanId}}'\n            apiProductId: '{{tools.apiProductId}}'\n      - name: delete-api-key\n        method: DELETE\n        description: Delete a specific API key\n        inputParameters:\n        - name: apiKeyId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API key to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n  \
  \  port: 8080\n    namespace: solo-io-gateway-ops-api\n    description: Unified REST API for Solo.io Gloo Gateway platform operations.\n    resources:\n    - path: /v1/upstreams\n      name: upstreams\n      description: Backend upstream service management\n      operations:\n      - method: GET\n        name: list-upstreams\n        description: List all upstream backend services\n        call: gloo-gateway.list-upstreams\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/upstreams/{namespace}/{name}\n      name: upstream-detail\n      description: Individual upstream details\n      operations:\n      - method: GET\n        name: get-upstream\n        description: Get upstream details\n        call: gloo-gateway.get-upstream\n        with:\n          namespace: rest.namespace\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/virtual-services\n\
  \      name: virtual-services\n      description: Virtual service routing rules\n      operations:\n      - method: GET\n        name: list-virtual-services\n        description: List all virtual services\n        call: gloo-gateway.list-virtual-services\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/virtual-services/{namespace}/{name}\n      name: virtual-service-detail\n      description: Individual virtual service configuration\n      operations:\n      - method: GET\n        name: get-virtual-service\n        description: Get virtual service details\n        call: gloo-gateway.get-virtual-service\n        with:\n          namespace: rest.namespace\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/route-tables\n      name: route-tables\n      description: Delegated route table management\n      operations:\n      - method:\
  \ GET\n        name: list-route-tables\n        description: List all route tables\n        call: gloo-gateway.list-route-tables\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/proxies\n      name: proxies\n      description: Compiled Envoy proxy configurations\n      operations:\n      - method: GET\n        name: list-proxies\n        description: List all proxies\n        call: gloo-gateway.list-proxies\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gateways\n      name: gateways\n      description: Gateway listener management\n      operations:\n      - method: GET\n        name: list-gateways\n        description: List all gateways\n        call: gloo-gateway.list-gateways\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/health\n      name: health\n      description: Control plane health\n      operations:\n      - method: GET\n        name: health-check\n        description: Check control plane health\n        call: gloo-gateway.health-check\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portal/apis\n      name: portal-apis\n      description: Developer portal API catalog\n      operations:\n      - method: GET\n        name: list-portal-apis\n        description: List APIs in developer portal\n        call: gloo-portal.list-apis\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/portal/usage-plans\n      name: portal-usage-plans\n      description: Developer portal usage plans\n      operations:\n      - method: GET\n        name: list-usage-plans\n        description: List usage plans\n        call: gloo-portal.list-usage-plans\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/portal/api-keys\n      name: portal-api-keys\n      description: Developer API key management\n      operations:\n      - method: GET\n        name: list-api-keys\n        description: List API keys\n        call: gloo-portal.list-api-keys\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-api-key\n        description: Create API key\n        call: gloo-portal.create-api-key\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: solo-io-gateway-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted Solo.io Gloo Gateway platform operations.\n    tools:\n    - name: list-upstreams\n      description: List all upstream backend services registered with Gloo Gateway, optionally filtered by namespace\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gloo-gateway.list-upstreams\n      with:\n   \
  \     namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-upstream\n      description: Get details of a specific upstream service including health checks and TLS config\n      hints:\n        readOnly: true\n      call: gloo-gateway.get-upstream\n      with:\n        namespace: tools.namespace\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-virtual-services\n      description: List all virtual services with domains, routing rules, and security policies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gloo-gateway.list-virtual-services\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-virtual-service\n      description: Get full virtual service configuration including routes, rate limiting, and authentication\n      hints:\n        readOnly: true\n      call:\
  \ gloo-gateway.get-virtual-service\n      with:\n        namespace: tools.namespace\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-route-tables\n      description: List route tables used for delegated routing configuration across teams\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gloo-gateway.list-route-tables\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-route-table\n      description: Get route table with all routes, matchers, and upstream destinations\n      hints:\n        readOnly: true\n      call: gloo-gateway.get-route-table\n      with:\n        namespace: tools.namespace\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-proxies\n      description: List compiled Envoy proxy configurations generated from gateway resources\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: gloo-gateway.list-proxies\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-proxy\n      description: Get compiled proxy configuration with all listeners, routes, and clusters\n      hints:\n        readOnly: true\n      call: gloo-gateway.get-proxy\n      with:\n        namespace: tools.namespace\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-gateways\n      description: List all gateway resources defining listener addresses, ports, and TLS\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gloo-gateway.list-gateways\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-gateway\n      description: Get gateway listener configuration including TLS settings and virtual service\
  \ bindings\n      hints:\n        readOnly: true\n      call: gloo-gateway.get-gateway\n      with:\n        namespace: tools.namespace\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gateway-health-check\n      description: Check health status of Gloo Gateway control plane and its components\n      hints:\n        readOnly: true\n      call: gloo-gateway.health-check\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-portal-apis\n      description: List all APIs published in the Gloo developer portal\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gloo-portal.list-apis\n      with:\n        offset: tools.offset\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-portal-api\n      description: Get details of a specific portal API including schema and usage plans\n      hints:\n        readOnly: true\n    \
  \  call: gloo-portal.get-api\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-portal-api-schema\n      description: Retrieve the OpenAPI or GraphQL schema for a portal API\n      hints:\n        readOnly: true\n      call: gloo-portal.get-api-schema\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-usage-plans\n      description: List available usage plans with rate limits and API product access\n      hints:\n        readOnly: true\n      call: gloo-portal.list-usage-plans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-keys\n      description: List API keys for the authenticated portal user\n      hints:\n        readOnly: true\n      call: gloo-portal.list-api-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-key\n      description: Create a new\
  \ API key for accessing an API product under a usage plan\n      hints:\n        readOnly: false\n      call: gloo-portal.create-api-key\n      with:\n        name: tools.name\n        usagePlanId: tools.usagePlanId\n        apiProductId: tools.apiProductId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-api-key\n      description: Permanently delete an API key, revoking access to the associated API product\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: gloo-portal.delete-api-key\n      with:\n        apiKeyId: tools.apiKeyId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
