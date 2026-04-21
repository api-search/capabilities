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
- list stages for a rest api
- get rest api
- list all usage plans
- amazon api gateway
- aws
- deploy rest api
- managing api keys, usage plans, and authorization
- create a new api key
- manages api lifecycle, deployments, and governance across the organization
- list usage plans
- list rest api deployments
- list http api routes
- create route
- list all backend integrations for an http api
- disconnect websocket client
- create http api
- list rest api stages
- api management
- list all usage plans and their api key associations
- list api keys
- list all http and websocket apis
- rest api management
- serverless
- get details of a specific rest api
- http and websocket api management
- get websocket connection info
- deployment
- deploy a rest api to a stage
- rest api stages
- creating, versioning, deploying, and retiring apis
- api gateway
- list routes
- create rest api
- create api key
- delete a rest api
- API Platform Engineer
- disconnect client
- rest api deployments
- get connection
- list deployments
- disconnect a websocket client from the api
- Backend Developer
- create a new route for an http api
- get websocket connection
- cloud
- list rest apis
- list all rest apis in the aws account
- delete rest api
- send websocket message
- list all rest apis
- create a new http or websocket api
- websocket api management and connection handling
- disconnect a websocket client
- usage plan management
- list stages
- http api route management
- list all api keys in the account
- websocket connection management
- create a new api key for access control
- list integrations
- list all api keys
- list deployments for a rest api
- list http apis
- api key management
- create a new rest api
- list all routes for an http api
- creates and configures apis for application services
- websocket
- unified workflow for creating, deploying, and managing rest and http apis
- get information about a connected websocket client
- rest
- create a new rest api in api gateway
- send a message to a connected websocket client
- list routes for an http api
- list deployment stages for a rest api
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
