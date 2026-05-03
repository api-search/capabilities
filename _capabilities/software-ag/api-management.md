---
api_specs:
- filename: webmethods-api-gateway-openapi.yml
  format: yaml
  label: webmethods-api-gateway
  slug: webmethods-api-gateway
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/software-ag/refs/heads/main/openapi/webmethods-api-gateway-openapi.yml
categories: []
consumed_apis:
- webmethods-api-gateway
description: Unified API management workflow for Software AG webMethods, combining API Gateway management operations for creating, activating, publishing, and monitoring APIs in enterprise integration environments. Designed for API platform administrators and integration engineers.
layout: capability
name: Software AG webMethods API Management
operations:
- description: List all APIs registered in the API Gateway
  method: GET
  name: list-apis
  path: /v1/apis
- description: Create a new API from spec file or URL
  method: POST
  name: create-api
  path: /v1/apis
- description: Get a specific API definition
  method: GET
  name: get-api
  path: /v1/apis/{apiId}
- description: Activate an API to make it available to consumers
  method: PUT
  name: activate-api
  path: /v1/apis/{apiId}/activate
- description: Deactivate an API to hide it from consumers
  method: PUT
  name: deactivate-api
  path: /v1/apis/{apiId}/deactivate
- description: Publish an API to the webMethods Developer Portal
  method: PUT
  name: publish-api
  path: /v1/apis/{apiId}/publish
- description: List all applications consuming this API
  method: GET
  name: list-api-applications
  path: /v1/apis/{apiId}/applications
personas: []
provider_name: Software AG
provider_slug: software-ag
search_terms:
- activate an api to expose it to api consumers
- integration platform
- deactivate api
- software ag
- get api
- create a new api from spec file or url
- applications consuming the api
- api management
- list apis
- individual api management
- publish an api to the webmethods developer portal for consumer discovery
- enterprise integration
- list all apis registered in the api gateway
- get full details of a specific api including its openapi definition
- manage apis in the webmethods api gateway
- api deactivation control
- api gateway
- list all apis registered in the webmethods api gateway with optional filtering
- activate an api to make it available to consumers
- create api
- api activation control
- list all applications consuming this api
- deactivate an api to hide it from consumers
- list all consumer applications subscribed to a specific api
- deactivate an api to remove it from consumer visibility
- ipaas
- api portal publishing
- get a specific api definition
- developer portal
- create a new api in the api gateway from an openapi, swagger, raml, or wsdl spec
- webmethods
- publish an api to the webmethods developer portal
- activate api
- list api applications
- publish api
slug: api-management
source_filename: api-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Software AG webMethods API Management\"\n  description: >-\n    Unified API management workflow for Software AG webMethods, combining API\n    Gateway management operations for creating, activating, publishing, and\n    monitoring APIs in enterprise integration environments. Designed for API\n    platform administrators and integration engineers.\n  tags:\n    - API Management\n    - Enterprise Integration\n    - webMethods\n    - Software AG\n    - API Gateway\n    - Developer Portal\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEBMETHODS_API_GATEWAY_USER: WEBMETHODS_API_GATEWAY_USER\n      WEBMETHODS_API_GATEWAY_PASSWORD: WEBMETHODS_API_GATEWAY_PASSWORD\n\ncapability:\n  consumes:\n    - import: webmethods-api-gateway\n      location: ./shared/webmethods-api-gateway.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: webmethods-api-management-api\n\
  \      description: \"Unified REST API for webMethods API lifecycle management.\"\n      resources:\n        - path: /v1/apis\n          name: apis\n          description: \"Manage APIs in the webMethods API Gateway\"\n          operations:\n            - method: GET\n              name: list-apis\n              description: \"List all APIs registered in the API Gateway\"\n              call: \"webmethods-api-gateway.list-apis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api\n              description: \"Create a new API from spec file or URL\"\n              call: \"webmethods-api-gateway.create-api\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apis/{apiId}\n          name: api\n          description: \"Individual API management\"\n          operations:\n            - method: GET\n              name:\
  \ get-api\n              description: \"Get a specific API definition\"\n              call: \"webmethods-api-gateway.get-api\"\n              with:\n                apiId: \"rest.apiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apis/{apiId}/activate\n          name: api-activation\n          description: \"API activation control\"\n          operations:\n            - method: PUT\n              name: activate-api\n              description: \"Activate an API to make it available to consumers\"\n              call: \"webmethods-api-gateway.activate-api\"\n              with:\n                apiId: \"rest.apiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apis/{apiId}/deactivate\n          name: api-deactivation\n          description: \"API deactivation control\"\n          operations:\n            - method: PUT\n              name:\
  \ deactivate-api\n              description: \"Deactivate an API to hide it from consumers\"\n              call: \"webmethods-api-gateway.deactivate-api\"\n              with:\n                apiId: \"rest.apiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apis/{apiId}/publish\n          name: api-publishing\n          description: \"API portal publishing\"\n          operations:\n            - method: PUT\n              name: publish-api\n              description: \"Publish an API to the webMethods Developer Portal\"\n              call: \"webmethods-api-gateway.publish-api\"\n              with:\n                apiId: \"rest.apiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apis/{apiId}/applications\n          name: api-applications\n          description: \"Applications consuming the API\"\n          operations:\n          \
  \  - method: GET\n              name: list-api-applications\n              description: \"List all applications consuming this API\"\n              call: \"webmethods-api-gateway.list-api-applications\"\n              with:\n                apiId: \"rest.apiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: webmethods-api-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted webMethods API lifecycle management.\"\n      tools:\n        - name: list-apis\n          description: \"List all APIs registered in the webMethods API Gateway with optional filtering\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"webmethods-api-gateway.list-apis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-api\n          description: \"Get full details of a specific\
  \ API including its OpenAPI definition\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"webmethods-api-gateway.get-api\"\n          with:\n            apiId: \"tools.apiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-api\n          description: \"Create a new API in the API Gateway from an OpenAPI, Swagger, RAML, or WSDL spec\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"webmethods-api-gateway.create-api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: activate-api\n          description: \"Activate an API to expose it to API consumers\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"webmethods-api-gateway.activate-api\"\n          with:\n            apiId: \"tools.apiId\"\n      \
  \    outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deactivate-api\n          description: \"Deactivate an API to remove it from consumer visibility\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"webmethods-api-gateway.deactivate-api\"\n          with:\n            apiId: \"tools.apiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-api\n          description: \"Publish an API to the webMethods Developer Portal for consumer discovery\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"webmethods-api-gateway.publish-api\"\n          with:\n            apiId: \"tools.apiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-applications\n          description: \"List all consumer applications\
  \ subscribed to a specific API\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"webmethods-api-gateway.list-api-applications\"\n          with:\n            apiId: \"tools.apiId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/software-ag/refs/heads/main/capabilities/api-management.yaml
tags:
- API Management
- Enterprise Integration
- webMethods
- Software AG
- API Gateway
- Developer Portal
tools:
- description: List all APIs registered in the webMethods API Gateway with optional filtering
  hints:
    openWorld: true
    readOnly: true
  name: list-apis
- description: Get full details of a specific API including its OpenAPI definition
  hints:
    openWorld: false
    readOnly: true
  name: get-api
- description: Create a new API in the API Gateway from an OpenAPI, Swagger, RAML, or WSDL spec
  hints:
    destructive: false
    readOnly: false
  name: create-api
- description: Activate an API to expose it to API consumers
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: activate-api
- description: Deactivate an API to remove it from consumer visibility
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: deactivate-api
- description: Publish an API to the webMethods Developer Portal for consumer discovery
  hints:
    destructive: false
    readOnly: false
  name: publish-api
- description: List all consumer applications subscribed to a specific API
  hints:
    openWorld: false
    readOnly: true
  name: list-api-applications
---
