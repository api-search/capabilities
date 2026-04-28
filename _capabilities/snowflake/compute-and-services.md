---
categories:
- container-orchestration
consumed_apis:
- snowflake-warehouse
- snowflake-compute-pool
- snowflake-service
- snowflake-image-repository
- snowflake-alert
description: Unified workflow for managing warehouses, compute pools, Snowpark Container Services, image repositories, and monitoring alerts. Used by Platform Engineers and DevOps teams to provision and operate compute infrastructure.
layout: capability
name: Snowflake Compute and Services
operations:
- description: List warehouses
  method: GET
  name: list-warehouses
  path: /v1/warehouses
- description: Create a warehouse
  method: POST
  name: create-warehouse
  path: /v1/warehouses
- description: List compute pools
  method: GET
  name: list-compute-pools
  path: /v1/compute-pools
- description: Create a compute pool
  method: POST
  name: create-compute-pool
  path: /v1/compute-pools
- description: List services
  method: GET
  name: list-services
  path: /v1/services
- description: Create a service
  method: POST
  name: create-service
  path: /v1/services
- description: List alerts
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: Create an alert
  method: POST
  name: create-alert
  path: /v1/alerts
personas: []
provider_name: Snowflake
provider_slug: snowflake
search_terms:
- data lakes
- fetch warehouse details
- sql
- compute pool management
- list monitoring alerts
- create an image repository
- create a service
- compute
- warehouse management
- create compute pool
- create a monitoring alert
- execute an alert
- list virtual warehouses
- delete a warehouse
- fetch service logs
- list services
- create an alert
- create service
- create warehouse
- alert management
- get service status
- fetch warehouse
- containers
- create a container service
- resume a suspended service
- create image repository
- execute alert
- container service management
- resume service
- fetch service status
- snowflake
- list image repositories
- list alerts
- suspend service
- suspend a running service
- list container services
- infrastructure
- list compute pools
- list warehouses
- get service logs
- create alert
- data warehousing
- database
- create a warehouse
- delete warehouse
- data sharing
- create a compute pool
- create a virtual warehouse
slug: compute-and-services
tags:
- Snowflake
- Compute
- Containers
- Infrastructure
tools:
- description: List virtual warehouses
  hints:
    readOnly: true
  name: list-warehouses
- description: Create a virtual warehouse
  hints:
    readOnly: false
  name: create-warehouse
- description: Fetch warehouse details
  hints:
    readOnly: true
  name: fetch-warehouse
- description: Delete a warehouse
  hints:
    destructive: true
  name: delete-warehouse
- description: List compute pools
  hints:
    readOnly: true
  name: list-compute-pools
- description: Create a compute pool
  hints:
    readOnly: false
  name: create-compute-pool
- description: List container services
  hints:
    readOnly: true
  name: list-services
- description: Create a container service
  hints:
    readOnly: false
  name: create-service
- description: Get service status
  hints:
    readOnly: true
  name: fetch-service-status
- description: Get service logs
  hints:
    readOnly: true
  name: fetch-service-logs
- description: Resume a suspended service
  hints:
    readOnly: false
  name: resume-service
- description: Suspend a running service
  hints:
    readOnly: false
  name: suspend-service
- description: List image repositories
  hints:
    readOnly: true
  name: list-image-repositories
- description: Create an image repository
  hints:
    readOnly: false
  name: create-image-repository
- description: List monitoring alerts
  hints:
    readOnly: true
  name: list-alerts
- description: Create a monitoring alert
  hints:
    readOnly: false
  name: create-alert
- description: Execute an alert
  hints:
    readOnly: false
  name: execute-alert
---
