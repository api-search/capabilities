---
categories: []
consumed_apis: []
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
- publish an api to the webmethods developer portal for consumer discovery
- list all consumer applications subscribed to a specific api
- deactivate an api to remove it from consumer visibility
- activate an api to expose it to api consumers
- developer portal
- webmethods
- get api
- publish an api to the webmethods developer portal
- activate an api to make it available to consumers
- create a new api from spec file or url
- enterprise integration
- publish api
- api deactivation control
- get a specific api definition
- create api
- create a new api in the api gateway from an openapi, swagger, raml, or wsdl spec
- list all apis registered in the api gateway
- api portal publishing
- applications consuming the api
- ipaas
- deactivate api
- get full details of a specific api including its openapi definition
- software ag
- list api applications
- activate api
- api gateway
- api activation control
- api management
- list all applications consuming this api
- list apis
- list all apis registered in the webmethods api gateway with optional filtering
- integration platform
- manage apis in the webmethods api gateway
- individual api management
- deactivate an api to hide it from consumers
slug: api-management
source_filename: api-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Software AG webMethods API Management\n  description: Unified API management workflow for Software AG webMethods, combining API Gateway management operations for\n    creating, activating, publishing, and monitoring APIs in enterprise integration environments. Designed for API platform\n    administrators and integration engineers.\n  tags:\n  - API Management\n  - Enterprise Integration\n  - webMethods\n  - Software AG\n  - API Gateway\n  - Developer Portal\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WEBMETHODS_API_GATEWAY_USER: WEBMETHODS_API_GATEWAY_USER\n    WEBMETHODS_API_GATEWAY_PASSWORD: WEBMETHODS_API_GATEWAY_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: webmethods-api-gateway\n    baseUri: http://localhost:5555/rest/apigateway\n    description: webMethods API Gateway Service Management REST API\n    authentication:\n      type: basic\n      username: '{{WEBMETHODS_API_GATEWAY_USER}}'\n\
  \      password: '{{WEBMETHODS_API_GATEWAY_PASSWORD}}'\n    resources:\n    - name: apis\n      path: /apis\n      description: API lifecycle management operations\n      operations:\n      - name: list-apis\n        method: GET\n        description: Retrieve all or filtered APIs with pagination\n        inputParameters:\n        - name: apiIds\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of API IDs to filter\n        - name: from\n          in: query\n          type: integer\n          required: false\n          description: Starting index for pagination\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api\n        method: POST\n        description: Create a new API from\
  \ file, URL, or from scratch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            apiName: '{{tools.apiName}}'\n            apiVersion: '{{tools.apiVersion}}'\n            apiDescription: '{{tools.apiDescription}}'\n    - name: api-by-id\n      path: /apis/{apiId}\n      description: Individual API management operations\n      operations:\n      - name: get-api\n        method: GET\n        description: Fetch a specific API definition\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Export format: swagger, raml, openapi, odata'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-api\n        method: PUT\n        description: Update an API definition preserving existing policies\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            apiName: '{{tools.apiName}}'\n            apiVersion: '{{tools.apiVersion}}'\n            apiDescription: '{{tools.apiDescription}}'\n      - name: delete-api\n        method: DELETE\n        description: Remove an inactive API from the gateway\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-activate\n      path: /apis/{apiId}/activate\n      description: API activation management\n      operations:\n      - name: activate-api\n        method: PUT\n        description: Expose an API to consumers by activating it\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-deactivate\n      path: /apis/{apiId}/deactivate\n      description: API deactivation management\n      operations:\n      - name: deactivate-api\n        method: PUT\n        description: Hide an API from consumers by deactivating it\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n         \
  \ required: true\n          description: Unique identifier of the API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-applications\n      path: /apis/{apiId}/applications\n      description: Applications consuming an API\n      operations:\n      - name: list-api-applications\n        method: GET\n        description: Retrieve all applications registered to consume this API\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-publish\n      path: /apis/{apiId}/publish\n      description: API portal publishing\n      operations:\n      - name: publish-api\n        method: PUT\n        description: Register an API to the webMethods Developer\
  \ Portal\n        inputParameters:\n        - name: apiId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            portalGatewayId: '{{tools.portalGatewayId}}'\n            communities: '{{tools.communities}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: webmethods-api-management-api\n    description: Unified REST API for webMethods API lifecycle management.\n    resources:\n    - path: /v1/apis\n      name: apis\n      description: Manage APIs in the webMethods API Gateway\n      operations:\n      - method: GET\n        name: list-apis\n        description: List all APIs registered in the API Gateway\n        call: webmethods-api-gateway.list-apis\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: create-api\n        description: Create a new API from spec file or URL\n        call: webmethods-api-gateway.create-api\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{apiId}\n      name: api\n      description: Individual API management\n      operations:\n      - method: GET\n        name: get-api\n        description: Get a specific API definition\n        call: webmethods-api-gateway.get-api\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{apiId}/activate\n      name: api-activation\n      description: API activation control\n      operations:\n      - method: PUT\n        name: activate-api\n        description: Activate an API to make it available to consumers\n        call: webmethods-api-gateway.activate-api\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/apis/{apiId}/deactivate\n      name: api-deactivation\n      description: API deactivation control\n      operations:\n      - method: PUT\n        name: deactivate-api\n        description: Deactivate an API to hide it from consumers\n        call: webmethods-api-gateway.deactivate-api\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{apiId}/publish\n      name: api-publishing\n      description: API portal publishing\n      operations:\n      - method: PUT\n        name: publish-api\n        description: Publish an API to the webMethods Developer Portal\n        call: webmethods-api-gateway.publish-api\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{apiId}/applications\n      name: api-applications\n      description: Applications consuming the API\n      operations:\n\
  \      - method: GET\n        name: list-api-applications\n        description: List all applications consuming this API\n        call: webmethods-api-gateway.list-api-applications\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: webmethods-api-management-mcp\n    transport: http\n    description: MCP server for AI-assisted webMethods API lifecycle management.\n    tools:\n    - name: list-apis\n      description: List all APIs registered in the webMethods API Gateway with optional filtering\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webmethods-api-gateway.list-apis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api\n      description: Get full details of a specific API including its OpenAPI definition\n      hints:\n        readOnly: true\n        openWorld: false\n      call: webmethods-api-gateway.get-api\n\
  \      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api\n      description: Create a new API in the API Gateway from an OpenAPI, Swagger, RAML, or WSDL spec\n      hints:\n        readOnly: false\n        destructive: false\n      call: webmethods-api-gateway.create-api\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activate-api\n      description: Activate an API to expose it to API consumers\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: webmethods-api-gateway.activate-api\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deactivate-api\n      description: Deactivate an API to remove it from consumer visibility\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: webmethods-api-gateway.deactivate-api\n\
  \      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-api\n      description: Publish an API to the webMethods Developer Portal for consumer discovery\n      hints:\n        readOnly: false\n        destructive: false\n      call: webmethods-api-gateway.publish-api\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-applications\n      description: List all consumer applications subscribed to a specific API\n      hints:\n        readOnly: true\n        openWorld: false\n      call: webmethods-api-gateway.list-api-applications\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
