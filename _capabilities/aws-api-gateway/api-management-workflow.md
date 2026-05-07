---
categories:
- api-management
consumed_apis: []
description: Unified workflow capability for API platform engineers and developers to create, configure, deploy, and monitor REST and HTTP APIs in Amazon API Gateway. Combines V1 REST APIs, V2 HTTP/WebSocket APIs, and the Management API for complete API lifecycle management including deployment orchestration and real-time WebSocket connection management.
layout: capability
name: Amazon API Gateway API Management Workflow
operations:
- description: List all REST APIs
  method: GET
  name: list-rest-apis
  path: /v1/rest-apis
- description: Create a new REST API
  method: POST
  name: create-rest-api
  path: /v1/rest-apis
- description: List deployments for a REST API
  method: GET
  name: list-rest-api-deployments
  path: /v1/rest-apis/{restapi_id}/deployments
- description: Deploy a REST API to a stage
  method: POST
  name: deploy-rest-api
  path: /v1/rest-apis/{restapi_id}/deployments
- description: List stages for a REST API
  method: GET
  name: list-rest-api-stages
  path: /v1/rest-apis/{restapi_id}/stages
- description: List all API keys
  method: GET
  name: list-api-keys
  path: /v1/api-keys
- description: Create a new API key
  method: POST
  name: create-api-key
  path: /v1/api-keys
- description: List all usage plans
  method: GET
  name: list-usage-plans
  path: /v1/usage-plans
- description: List all HTTP and WebSocket APIs
  method: GET
  name: list-http-apis
  path: /v1/http-apis
- description: Create a new HTTP or WebSocket API
  method: POST
  name: create-http-api
  path: /v1/http-apis
- description: List routes for an HTTP API
  method: GET
  name: list-routes
  path: /v1/http-apis/{api_id}/routes
- description: Get WebSocket connection info
  method: GET
  name: get-connection
  path: /v1/connections/{connectionId}
- description: Disconnect a WebSocket client
  method: DELETE
  name: disconnect-client
  path: /v1/connections/{connectionId}
personas: []
provider_name: Amazon API Gateway
provider_slug: aws-api-gateway
search_terms:
- list integrations
- create a new api key for access control
- disconnect websocket client
- websocket
- API Platform Engineer
- list usage plans
- create a new route for an http api
- list rest api stages
- api key management
- unified workflow for creating, deploying, and managing rest and http apis
- http api route management
- list all backend integrations for an http api
- rest api management
- list all api keys
- list all routes for an http api
- creating, versioning, deploying, and retiring apis
- create route
- rest
- get websocket connection info
- managing api keys, usage plans, and authorization
- api management
- list rest apis
- list all http and websocket apis
- deployment
- disconnect client
- send websocket message
- get websocket connection
- manages api lifecycle, deployments, and governance across the organization
- Backend Developer
- disconnect a websocket client
- serverless
- websocket connection management
- get details of a specific rest api
- rest api stages
- get rest api
- delete rest api
- list deployments
- list deployment stages for a rest api
- list http api routes
- disconnect a websocket client from the api
- list routes
- deploy a rest api to a stage
- create a new rest api in api gateway
- get information about a connected websocket client
- creates and configures apis for application services
- send a message to a connected websocket client
- api gateway
- list all usage plans
- list all rest apis in the aws account
- amazon api gateway
- list api keys
- usage plan management
- cloud
- deploy rest api
- create api key
- list all rest apis
- list all api keys in the account
- list all usage plans and their api key associations
- list http apis
- create a new http or websocket api
- get connection
- aws
- rest api deployments
- http and websocket api management
- list routes for an http api
- create http api
- list rest api deployments
- create a new rest api
- delete a rest api
- websocket api management and connection handling
- create a new api key
- list stages
- list deployments for a rest api
- create rest api
- list stages for a rest api
slug: api-management-workflow
source_filename: api-management-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon API Gateway API Management Workflow\n  description: Unified workflow capability for API platform engineers and developers to create, configure, deploy, and monitor\n    REST and HTTP APIs in Amazon API Gateway. Combines V1 REST APIs, V2 HTTP/WebSocket APIs, and the Management API for complete\n    API lifecycle management including deployment orchestration and real-time WebSocket connection management.\n  tags:\n  - Amazon API Gateway\n  - AWS\n  - API Management\n  - REST\n  - WebSocket\n  - Deployment\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\n    API_GATEWAY_ENDPOINT: API_GATEWAY_ENDPOINT\ncapability:\n  consumes:\n  - type: http\n    namespace: api-gateway-v1\n    baseUri: https://apigateway.{region}.amazonaws.com\n    description: Amazon API Gateway V1 REST control\
  \ plane API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_SIGV4_TOKEN}}'\n      placement: header\n    resources:\n    - name: rest-apis\n      path: /restapis\n      description: Manage REST API definitions\n      operations:\n      - name: get-rest-apis\n        method: GET\n        description: List all REST APIs in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-rest-api\n        method: POST\n        description: Create a new REST API\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-api\n      path: /restapis/{restapi_id}\n      description: Manage a specific REST API\n      operations:\n      - name:\
  \ get-rest-api\n        method: GET\n        description: Get a specific REST API by ID\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The REST API identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-rest-api\n        method: DELETE\n        description: Delete a REST API\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The REST API identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /restapis/{restapi_id}/deployments\n      description: Manage API deployments\n      operations:\n      - name: get-deployments\n        method: GET\n        description: List all deployments\
  \ for a REST API\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The REST API identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Create a new deployment for a REST API\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The REST API identifier\n        body:\n          type: json\n          data:\n            stageName: '{{tools.stage_name}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stages\n      path: /restapis/{restapi_id}/stages\n      description: Manage API stages\n      operations:\n\
  \      - name: get-stages\n        method: GET\n        description: List all stages for a REST API\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The REST API identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-keys\n      path: /apikeys\n      description: Manage API keys\n      operations:\n      - name: get-api-keys\n        method: GET\n        description: List all API keys in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-key\n        method: POST\n        description: Create a new API key\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            enabled: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: usage-plans\n      path: /usageplans\n      description: Manage usage plans\n      operations:\n      - name: get-usage-plans\n        method: GET\n        description: List all usage plans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: api-gateway-v2\n    baseUri: https://apigateway.{region}.amazonaws.com\n    description: Amazon API Gateway V2 HTTP and WebSocket control plane API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_SIGV4_TOKEN}}'\n      placement: header\n    resources:\n    - name: apis\n      path: /v2/apis\n      description: Manage HTTP and WebSocket APIs\n      operations:\n      - name: get-apis\n        method: GET\n        description: List all HTTP and WebSocket APIs\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: create-api\n        method: POST\n        description: Create a new HTTP or WebSocket API\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            protocolType: '{{tools.protocol_type}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes\n      path: /v2/apis/{api_id}/routes\n      description: Manage API routes\n      operations:\n      - name: get-routes\n        method: GET\n        description: List all routes for an API\n        inputParameters:\n        - name: api_id\n          in: path\n          type: string\n          required: true\n          description: The API identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-route\n        method: POST\n        description:\
  \ Create a new route for an API\n        inputParameters:\n        - name: api_id\n          in: path\n          type: string\n          required: true\n          description: The API identifier\n        body:\n          type: json\n          data:\n            routeKey: '{{tools.route_key}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integrations\n      path: /v2/apis/{api_id}/integrations\n      description: Manage API integrations\n      operations:\n      - name: get-integrations\n        method: GET\n        description: List all integrations for an API\n        inputParameters:\n        - name: api_id\n          in: path\n          type: string\n          required: true\n          description: The API identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stages-v2\n      path: /v2/apis/{api_id}/stages\n\
  \      description: Manage API stages\n      operations:\n      - name: get-stages\n        method: GET\n        description: List all stages for an API\n        inputParameters:\n        - name: api_id\n          in: path\n          type: string\n          required: true\n          description: The API identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: api-gateway-mgmt\n    baseUri: https://{api-id}.execute-api.{region}.amazonaws.com/{stage}\n    description: Amazon API Gateway Management API for WebSocket connection management\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_SIGV4_TOKEN}}'\n      placement: header\n    resources:\n    - name: connections\n      path: /@connections/{connectionId}\n      description: Manage WebSocket connections\n      operations:\n      - name: get-connection\n        method: GET\n        description:\
  \ Get information about a connected WebSocket client\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: The connection identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-to-connection\n        method: POST\n        description: Send a message to a connected WebSocket client\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: The connection identifier\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-connection\n        method: DELETE\n        description: Disconnect a connected WebSocket client\n\
  \        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: The connection identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: api-gateway-workflow-api\n    description: Unified REST API for Amazon API Gateway lifecycle management.\n    resources:\n    - path: /v1/rest-apis\n      name: rest-apis\n      description: REST API management\n      operations:\n      - method: GET\n        name: list-rest-apis\n        description: List all REST APIs\n        call: api-gateway-v1.get-rest-apis\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-rest-api\n        description: Create a new REST API\n        call: api-gateway-v1.create-rest-api\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /v1/rest-apis/{restapi_id}/deployments\n      name: rest-api-deployments\n      description: REST API deployments\n      operations:\n      - method: GET\n        name: list-rest-api-deployments\n        description: List deployments for a REST API\n        call: api-gateway-v1.get-deployments\n        with:\n          restapi_id: rest.restapi_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: deploy-rest-api\n        description: Deploy a REST API to a stage\n        call: api-gateway-v1.create-deployment\n        with:\n          restapi_id: rest.restapi_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rest-apis/{restapi_id}/stages\n      name: rest-api-stages\n      description: REST API stages\n      operations:\n      - method: GET\n        name: list-rest-api-stages\n        description: List stages for a REST API\n        call: api-gateway-v1.get-stages\n\
  \        with:\n          restapi_id: rest.restapi_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys\n      name: api-keys\n      description: API key management\n      operations:\n      - method: GET\n        name: list-api-keys\n        description: List all API keys\n        call: api-gateway-v1.get-api-keys\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-api-key\n        description: Create a new API key\n        call: api-gateway-v1.create-api-key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/usage-plans\n      name: usage-plans\n      description: Usage plan management\n      operations:\n      - method: GET\n        name: list-usage-plans\n        description: List all usage plans\n        call: api-gateway-v1.get-usage-plans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/http-apis\n\
  \      name: http-apis\n      description: HTTP and WebSocket API management\n      operations:\n      - method: GET\n        name: list-http-apis\n        description: List all HTTP and WebSocket APIs\n        call: api-gateway-v2.get-apis\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-http-api\n        description: Create a new HTTP or WebSocket API\n        call: api-gateway-v2.create-api\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/http-apis/{api_id}/routes\n      name: http-api-routes\n      description: HTTP API route management\n      operations:\n      - method: GET\n        name: list-routes\n        description: List routes for an HTTP API\n        call: api-gateway-v2.get-routes\n        with:\n          api_id: rest.api_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections/{connectionId}\n      name: websocket-connections\n\
  \      description: WebSocket connection management\n      operations:\n      - method: GET\n        name: get-connection\n        description: Get WebSocket connection info\n        call: api-gateway-mgmt.get-connection\n        with:\n          connectionId: rest.connectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: disconnect-client\n        description: Disconnect a WebSocket client\n        call: api-gateway-mgmt.delete-connection\n        with:\n          connectionId: rest.connectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: api-gateway-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon API Gateway lifecycle management.\n    tools:\n    - name: list-rest-apis\n      description: List all REST APIs in the AWS account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: api-gateway-v1.get-rest-apis\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-rest-api\n      description: Create a new REST API in API Gateway\n      hints:\n        readOnly: false\n      call: api-gateway-v1.create-rest-api\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rest-api\n      description: Get details of a specific REST API\n      hints:\n        readOnly: true\n      call: api-gateway-v1.get-rest-api\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-rest-api\n      description: Delete a REST API\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: api-gateway-v1.delete-rest-api\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deployments\n      description: List deployments for a REST API\n      hints:\n        readOnly: true\n      call: api-gateway-v1.get-deployments\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n    - name: deploy-rest-api\n      description: Deploy a REST API to a stage\n      hints:\n        readOnly: false\n      call: api-gateway-v1.create-deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stages\n      description: List deployment stages for a REST API\n      hints:\n        readOnly: true\n      call: api-gateway-v1.get-stages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-keys\n      description: List all API keys in the account\n      hints:\n        readOnly: true\n      call: api-gateway-v1.get-api-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-key\n      description: Create a new API key for access control\n      hints:\n        readOnly: false\n      call: api-gateway-v1.create-api-key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-usage-plans\n      description:\
  \ List all usage plans and their API key associations\n      hints:\n        readOnly: true\n      call: api-gateway-v1.get-usage-plans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-http-apis\n      description: List all HTTP and WebSocket APIs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: api-gateway-v2.get-apis\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-http-api\n      description: Create a new HTTP or WebSocket API\n      hints:\n        readOnly: false\n      call: api-gateway-v2.create-api\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-http-api-routes\n      description: List all routes for an HTTP API\n      hints:\n        readOnly: true\n      call: api-gateway-v2.get-routes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-route\n      description: Create a new route for an HTTP API\n   \
  \   hints:\n        readOnly: false\n      call: api-gateway-v2.create-route\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-integrations\n      description: List all backend integrations for an HTTP API\n      hints:\n        readOnly: true\n      call: api-gateway-v2.get-integrations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-websocket-connection\n      description: Get information about a connected WebSocket client\n      hints:\n        readOnly: true\n      call: api-gateway-mgmt.get-connection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-websocket-message\n      description: Send a message to a connected WebSocket client\n      hints:\n        readOnly: false\n        destructive: false\n      call: api-gateway-mgmt.post-to-connection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disconnect-websocket-client\n      description:\
  \ Disconnect a WebSocket client from the API\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: api-gateway-mgmt.delete-connection\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-api-gateway/refs/heads/main/capabilities/api-management-workflow.yaml
tags:
- Amazon API Gateway
- API Management
- REST
- WebSocket
- Deployment
tools:
- description: List all REST APIs in the AWS account
  hints:
    openWorld: true
    readOnly: true
  name: list-rest-apis
- description: Create a new REST API in API Gateway
  hints:
    readOnly: false
  name: create-rest-api
- description: Get details of a specific REST API
  hints:
    readOnly: true
  name: get-rest-api
- description: Delete a REST API
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-rest-api
- description: List deployments for a REST API
  hints:
    readOnly: true
  name: list-deployments
- description: Deploy a REST API to a stage
  hints:
    readOnly: false
  name: deploy-rest-api
- description: List deployment stages for a REST API
  hints:
    readOnly: true
  name: list-stages
- description: List all API keys in the account
  hints:
    readOnly: true
  name: list-api-keys
- description: Create a new API key for access control
  hints:
    readOnly: false
  name: create-api-key
- description: List all usage plans and their API key associations
  hints:
    readOnly: true
  name: list-usage-plans
- description: List all HTTP and WebSocket APIs
  hints:
    openWorld: true
    readOnly: true
  name: list-http-apis
- description: Create a new HTTP or WebSocket API
  hints:
    readOnly: false
  name: create-http-api
- description: List all routes for an HTTP API
  hints:
    readOnly: true
  name: list-http-api-routes
- description: Create a new route for an HTTP API
  hints:
    readOnly: false
  name: create-route
- description: List all backend integrations for an HTTP API
  hints:
    readOnly: true
  name: list-integrations
- description: Get information about a connected WebSocket client
  hints:
    readOnly: true
  name: get-websocket-connection
- description: Send a message to a connected WebSocket client
  hints:
    destructive: false
    readOnly: false
  name: send-websocket-message
- description: Disconnect a WebSocket client from the API
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disconnect-websocket-client
---
