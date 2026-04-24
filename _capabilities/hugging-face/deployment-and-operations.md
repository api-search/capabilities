---
consumed_apis:
- hf-endpoints
- hf-tgi
description: Unified workflow for deploying, scaling, and operating ML model inference endpoints on dedicated infrastructure. Combines Inference Endpoints management with TGI server monitoring. Used by ML platform engineers and DevOps teams.
layout: capability
name: Hugging Face Deployment and Operations
operations:
- description: List all endpoints
  method: GET
  name: list-endpoints
  path: /v1/endpoints/{namespace}
- description: Create a new endpoint
  method: POST
  name: create-endpoint
  path: /v1/endpoints/{namespace}
- description: Get endpoint details
  method: GET
  name: get-endpoint
  path: /v1/endpoints/{namespace}/{endpoint_name}
- description: Update endpoint configuration
  method: PUT
  name: update-endpoint
  path: /v1/endpoints/{namespace}/{endpoint_name}
- description: Delete an endpoint
  method: DELETE
  name: delete-endpoint
  path: /v1/endpoints/{namespace}/{endpoint_name}
- description: Pause a running endpoint
  method: POST
  name: pause-endpoint
  path: /v1/endpoints/{namespace}/{endpoint_name}/pause
- description: Resume a paused endpoint
  method: POST
  name: resume-endpoint
  path: /v1/endpoints/{namespace}/{endpoint_name}/resume
- description: Get endpoint logs
  method: GET
  name: get-logs
  path: /v1/endpoints/{namespace}/{endpoint_name}/logs
- description: Get endpoint metrics
  method: GET
  name: get-metrics
  path: /v1/endpoints/{namespace}/{endpoint_name}/metrics
- description: Check TGI server health
  method: GET
  name: health-check
  path: /v1/server/health
- description: Get TGI server info
  method: GET
  name: get-info
  path: /v1/server/info
- description: List available cloud providers
  method: GET
  name: list-providers
  path: /v1/providers
personas: []
provider_name: Hugging Face
provider_slug: hugging-face
search_terms:
- manage inference endpoints
- create a new endpoint
- pause a running endpoint
- get information about the deployed model and tgi server.
- get details of a specific endpoint.
- delete an endpoint
- get endpoint
- update an existing endpoint configuration.
- resume a paused endpoint.
- update endpoint
- get logs
- tgi server health
- list providers
- mlops
- individual endpoint operations
- get metrics for an endpoint.
- resume endpoint
- get info
- tgi server info
- cloud providers
- get tgi server info
- list all dedicated inference endpoints for a namespace.
- scale to zero
- hugging face
- get endpoint metrics
- list available cloud providers and hardware options.
- create a new dedicated inference endpoint.
- pause a running endpoint to stop billing.
- deployment
- scale an endpoint to zero replicas.
- tgi health check
- get endpoint logs
- update endpoint configuration
- get metrics
- list available cloud providers
- delete endpoint
- get prometheus metrics from the tgi server.
- check if the tgi server is healthy and responding.
- resume a paused endpoint
- list endpoints
- health check
- resume an endpoint
- delete a dedicated inference endpoint.
- get logs for an endpoint.
- tgi metrics
- operations
- get endpoint details
- pause endpoint
- list all endpoints
- create endpoint
- pause an endpoint
- check tgi server health
- infrastructure
slug: deployment-and-operations
tags:
- Hugging Face
- Deployment
- Operations
- Infrastructure
- MLOps
tools:
- description: List all dedicated inference endpoints for a namespace.
  hints:
    openWorld: true
    readOnly: true
  name: list-endpoints
- description: Create a new dedicated inference endpoint.
  hints:
    readOnly: false
  name: create-endpoint
- description: Get details of a specific endpoint.
  hints:
    openWorld: true
    readOnly: true
  name: get-endpoint
- description: Update an existing endpoint configuration.
  hints:
    idempotent: true
    readOnly: false
  name: update-endpoint
- description: Delete a dedicated inference endpoint.
  hints:
    destructive: true
    readOnly: false
  name: delete-endpoint
- description: Pause a running endpoint to stop billing.
  hints:
    readOnly: false
  name: pause-endpoint
- description: Resume a paused endpoint.
  hints:
    readOnly: false
  name: resume-endpoint
- description: Scale an endpoint to zero replicas.
  hints:
    readOnly: false
  name: scale-to-zero
- description: Get logs for an endpoint.
  hints:
    readOnly: true
  name: get-endpoint-logs
- description: Get metrics for an endpoint.
  hints:
    readOnly: true
  name: get-endpoint-metrics
- description: List available cloud providers and hardware options.
  hints:
    readOnly: true
  name: list-providers
- description: Check if the TGI server is healthy and responding.
  hints:
    readOnly: true
  name: tgi-health-check
- description: Get information about the deployed model and TGI server.
  hints:
    readOnly: true
  name: tgi-server-info
- description: Get Prometheus metrics from the TGI server.
  hints:
    readOnly: true
  name: tgi-metrics
---
