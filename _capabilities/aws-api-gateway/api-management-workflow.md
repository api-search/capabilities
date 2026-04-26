---
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
- create a new rest api
- deploy rest api
- create http api
- list all backend integrations for an http api
- API Platform Engineer
- unified workflow for creating, deploying, and managing rest and http apis
- list all usage plans and their api key associations
- deploy a rest api to a stage
- list http api routes
- serverless
- list rest apis
- list routes
- list all rest apis
- disconnect client
- list deployments
- websocket
- get websocket connection
- send websocket message
- websocket api management and connection handling
- disconnect websocket client
- delete a rest api
- get websocket connection info
- cloud
- list rest api deployments
- get rest api
- create a new api key for access control
- manages api lifecycle, deployments, and governance across the organization
- list all http and websocket apis
- list http apis
- aws
- api key management
- usage plan management
- http api route management
- http and websocket api management
- create route
- rest api deployments
- list all usage plans
- list deployments for a rest api
- list deployment stages for a rest api
- api management
- list integrations
- websocket connection management
- list routes for an http api
- list all api keys in the account
- list all api keys
- list all routes for an http api
- rest api stages
- create a new route for an http api
- delete rest api
- create a new rest api in api gateway
- send a message to a connected websocket client
- api gateway
- list api keys
- amazon api gateway
- creates and configures apis for application services
- create rest api
- list rest api stages
- list stages
- rest
- get information about a connected websocket client
- get details of a specific rest api
- disconnect a websocket client from the api
- list stages for a rest api
- disconnect a websocket client
- get connection
- create a new http or websocket api
- Backend Developer
- list all rest apis in the aws account
- create a new api key
- list usage plans
- rest api management
- deployment
- managing api keys, usage plans, and authorization
- create api key
- creating, versioning, deploying, and retiring apis
slug: api-management-workflow
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
