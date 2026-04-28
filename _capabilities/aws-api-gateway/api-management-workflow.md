---
categories:
- api-management
consumed_apis:
- api-gateway-v1
- api-gateway-v2
- api-gateway-mgmt
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
- list rest api stages
- rest api stages
- list rest apis
- rest api deployments
- unified workflow for creating, deploying, and managing rest and http apis
- create http api
- disconnect a websocket client
- delete rest api
- amazon api gateway
- deploy rest api
- Backend Developer
- serverless
- get details of a specific rest api
- list stages for a rest api
- create a new rest api
- rest
- create a new rest api in api gateway
- disconnect a websocket client from the api
- list all rest apis
- create api key
- list all http and websocket apis
- list rest api deployments
- create a new http or websocket api
- list http api routes
- creates and configures apis for application services
- aws
- list deployment stages for a rest api
- create a new api key
- list integrations
- deployment
- list all usage plans and their api key associations
- http and websocket api management
- delete a rest api
- http api route management
- disconnect websocket client
- api gateway
- create a new route for an http api
- list all backend integrations for an http api
- rest api management
- websocket connection management
- websocket api management and connection handling
- cloud
- list deployments for a rest api
- create a new api key for access control
- list routes
- create route
- websocket
- disconnect client
- get information about a connected websocket client
- deploy a rest api to a stage
- get rest api
- api key management
- usage plan management
- get connection
- list all usage plans
- get websocket connection info
- list all api keys in the account
- list usage plans
- list api keys
- list http apis
- list all api keys
- send a message to a connected websocket client
- send websocket message
- API Platform Engineer
- creating, versioning, deploying, and retiring apis
- managing api keys, usage plans, and authorization
- list deployments
- list stages
- get websocket connection
- list all rest apis in the aws account
- create rest api
- manages api lifecycle, deployments, and governance across the organization
- list routes for an http api
- api management
- list all routes for an http api
slug: api-management-workflow
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon API Gateway API Management Workflow\"\n  description: \"Unified workflow capability for API platform engineers and developers to create, configure, deploy, and monitor REST and HTTP APIs in Amazon API Gateway. Combines V1 REST APIs, V2 HTTP/WebSocket APIs, and the Management API for complete API lifecycle management including deployment orchestration and real-time WebSocket connection management.\"\n  tags:\n    - Amazon API Gateway\n    - AWS\n    - API Management\n    - REST\n    - WebSocket\n    - Deployment\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n      API_GATEWAY_ENDPOINT: API_GATEWAY_ENDPOINT\n\ncapability:\n  consumes:\n    - import: api-gateway-v1\n      location: ./shared/api-gateway-v1.yaml\n    - import: api-gateway-v2\n      location:\
  \ ./shared/api-gateway-v2.yaml\n    - import: api-gateway-mgmt\n      location: ./shared/api-gateway-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: api-gateway-workflow-api\n      description: \"Unified REST API for Amazon API Gateway lifecycle management.\"\n      resources:\n        - path: /v1/rest-apis\n          name: rest-apis\n          description: \"REST API management\"\n          operations:\n            - method: GET\n              name: list-rest-apis\n              description: \"List all REST APIs\"\n              call: \"api-gateway-v1.get-rest-apis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-rest-api\n              description: \"Create a new REST API\"\n              call: \"api-gateway-v1.create-rest-api\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/rest-apis/{restapi_id}/deployments\n          name: rest-api-deployments\n          description: \"REST API deployments\"\n          operations:\n            - method: GET\n              name: list-rest-api-deployments\n              description: \"List deployments for a REST API\"\n              call: \"api-gateway-v1.get-deployments\"\n              with:\n                restapi_id: \"rest.restapi_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: deploy-rest-api\n              description: \"Deploy a REST API to a stage\"\n              call: \"api-gateway-v1.create-deployment\"\n              with:\n                restapi_id: \"rest.restapi_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rest-apis/{restapi_id}/stages\n          name: rest-api-stages\n          description: \"REST API stages\"\n \
  \         operations:\n            - method: GET\n              name: list-rest-api-stages\n              description: \"List stages for a REST API\"\n              call: \"api-gateway-v1.get-stages\"\n              with:\n                restapi_id: \"rest.restapi_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/api-keys\n          name: api-keys\n          description: \"API key management\"\n          operations:\n            - method: GET\n              name: list-api-keys\n              description: \"List all API keys\"\n              call: \"api-gateway-v1.get-api-keys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-api-key\n              description: \"Create a new API key\"\n              call: \"api-gateway-v1.create-api-key\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/usage-plans\n          name: usage-plans\n          description: \"Usage plan management\"\n          operations:\n            - method: GET\n              name: list-usage-plans\n              description: \"List all usage plans\"\n              call: \"api-gateway-v1.get-usage-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-apis\n          name: http-apis\n          description: \"HTTP and WebSocket API management\"\n          operations:\n            - method: GET\n              name: list-http-apis\n              description: \"List all HTTP and WebSocket APIs\"\n              call: \"api-gateway-v2.get-apis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-http-api\n              description: \"Create a new HTTP or WebSocket API\"\n  \
  \            call: \"api-gateway-v2.create-api\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/http-apis/{api_id}/routes\n          name: http-api-routes\n          description: \"HTTP API route management\"\n          operations:\n            - method: GET\n              name: list-routes\n              description: \"List routes for an HTTP API\"\n              call: \"api-gateway-v2.get-routes\"\n              with:\n                api_id: \"rest.api_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connections/{connectionId}\n          name: websocket-connections\n          description: \"WebSocket connection management\"\n          operations:\n            - method: GET\n              name: get-connection\n              description: \"Get WebSocket connection info\"\n              call: \"api-gateway-mgmt.get-connection\"\n       \
  \       with:\n                connectionId: \"rest.connectionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: disconnect-client\n              description: \"Disconnect a WebSocket client\"\n              call: \"api-gateway-mgmt.delete-connection\"\n              with:\n                connectionId: \"rest.connectionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: api-gateway-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon API Gateway lifecycle management.\"\n      tools:\n        - name: list-rest-apis\n          description: \"List all REST APIs in the AWS account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"api-gateway-v1.get-rest-apis\"\n          outputParameters:\n     \
  \       - type: object\n              mapping: \"$.\"\n        - name: create-rest-api\n          description: \"Create a new REST API in API Gateway\"\n          hints:\n            readOnly: false\n          call: \"api-gateway-v1.create-rest-api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-rest-api\n          description: \"Get details of a specific REST API\"\n          hints:\n            readOnly: true\n          call: \"api-gateway-v1.get-rest-api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-rest-api\n          description: \"Delete a REST API\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"api-gateway-v1.delete-rest-api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-deployments\n          description:\
  \ \"List deployments for a REST API\"\n          hints:\n            readOnly: true\n          call: \"api-gateway-v1.get-deployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deploy-rest-api\n          description: \"Deploy a REST API to a stage\"\n          hints:\n            readOnly: false\n          call: \"api-gateway-v1.create-deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-stages\n          description: \"List deployment stages for a REST API\"\n          hints:\n            readOnly: true\n          call: \"api-gateway-v1.get-stages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-keys\n          description: \"List all API keys in the account\"\n          hints:\n            readOnly: true\n          call: \"api-gateway-v1.get-api-keys\"\n          outputParameters:\n   \
  \         - type: object\n              mapping: \"$.\"\n        - name: create-api-key\n          description: \"Create a new API key for access control\"\n          hints:\n            readOnly: false\n          call: \"api-gateway-v1.create-api-key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-usage-plans\n          description: \"List all usage plans and their API key associations\"\n          hints:\n            readOnly: true\n          call: \"api-gateway-v1.get-usage-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-http-apis\n          description: \"List all HTTP and WebSocket APIs\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"api-gateway-v2.get-apis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-http-api\n          description:\
  \ \"Create a new HTTP or WebSocket API\"\n          hints:\n            readOnly: false\n          call: \"api-gateway-v2.create-api\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-http-api-routes\n          description: \"List all routes for an HTTP API\"\n          hints:\n            readOnly: true\n          call: \"api-gateway-v2.get-routes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-route\n          description: \"Create a new route for an HTTP API\"\n          hints:\n            readOnly: false\n          call: \"api-gateway-v2.create-route\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-integrations\n          description: \"List all backend integrations for an HTTP API\"\n          hints:\n            readOnly: true\n          call: \"api-gateway-v2.get-integrations\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-websocket-connection\n          description: \"Get information about a connected WebSocket client\"\n          hints:\n            readOnly: true\n          call: \"api-gateway-mgmt.get-connection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-websocket-message\n          description: \"Send a message to a connected WebSocket client\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"api-gateway-mgmt.post-to-connection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: disconnect-websocket-client\n          description: \"Disconnect a WebSocket client from the API\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"api-gateway-mgmt.delete-connection\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-api-gateway/refs/heads/main/capabilities/api-management-workflow.yaml
tags:
- Amazon API Gateway
- AWS
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
