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
- resume service
- infrastructure
- snowflake
- database
- warehouse management
- resume a suspended service
- data lakes
- execute an alert
- fetch service status
- fetch service logs
- execute alert
- create a warehouse
- create an image repository
- create a service
- list compute pools
- delete a warehouse
- suspend a running service
- fetch warehouse details
- container service management
- containers
- create compute pool
- list monitoring alerts
- list alerts
- compute pool management
- fetch warehouse
- compute
- create an alert
- list warehouses
- suspend service
- data warehousing
- get service status
- sql
- delete warehouse
- create a virtual warehouse
- create a compute pool
- create image repository
- list image repositories
- list container services
- get service logs
- create a container service
- create alert
- create a monitoring alert
- create warehouse
- list services
- list virtual warehouses
- data sharing
- create service
- alert management
slug: compute-and-services
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowflake Compute and Services\"\n  description: \"Unified workflow for managing warehouses, compute pools, Snowpark Container Services, image repositories, and monitoring alerts. Used by Platform Engineers and DevOps teams to provision and operate compute infrastructure.\"\n  tags:\n    - Snowflake\n    - Compute\n    - Containers\n    - Infrastructure\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n      SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: snowflake-warehouse\n      location: ./shared/warehouse.yaml\n    - import: snowflake-compute-pool\n      location: ./shared/compute-pool.yaml\n    - import: snowflake-service\n      location: ./shared/service.yaml\n    - import: snowflake-image-repository\n      location: ./shared/image-repository.yaml\n    - import: snowflake-alert\n      location:\
  \ ./shared/alert.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: snowflake-compute-api\n      description: \"Unified REST API for Snowflake compute and services management.\"\n      resources:\n        - path: /v1/warehouses\n          name: warehouses\n          description: \"Warehouse management\"\n          operations:\n            - method: GET\n              name: list-warehouses\n              description: \"List warehouses\"\n              call: \"snowflake-warehouse.list-warehouses\"\n            - method: POST\n              name: create-warehouse\n              description: \"Create a warehouse\"\n              call: \"snowflake-warehouse.create-warehouse\"\n        - path: /v1/compute-pools\n          name: compute-pools\n          description: \"Compute pool management\"\n          operations:\n            - method: GET\n              name: list-compute-pools\n              description: \"List compute pools\"\n              call: \"snowflake-compute-pool.list-compute-pools\"\
  \n            - method: POST\n              name: create-compute-pool\n              description: \"Create a compute pool\"\n              call: \"snowflake-compute-pool.create-compute-pool\"\n        - path: /v1/services\n          name: services\n          description: \"Container service management\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List services\"\n              call: \"snowflake-service.list-services\"\n            - method: POST\n              name: create-service\n              description: \"Create a service\"\n              call: \"snowflake-service.create-service\"\n        - path: /v1/alerts\n          name: alerts\n          description: \"Alert management\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description: \"List alerts\"\n              call: \"snowflake-alert.list-alerts\"\n            - method: POST\n              name: create-alert\n\
  \              description: \"Create an alert\"\n              call: \"snowflake-alert.create-alert\"\n\n    - type: mcp\n      port: 9084\n      namespace: snowflake-compute-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Snowflake compute and services management.\"\n      tools:\n        - name: list-warehouses\n          description: \"List virtual warehouses\"\n          hints:\n            readOnly: true\n          call: \"snowflake-warehouse.list-warehouses\"\n        - name: create-warehouse\n          description: \"Create a virtual warehouse\"\n          hints:\n            readOnly: false\n          call: \"snowflake-warehouse.create-warehouse\"\n        - name: fetch-warehouse\n          description: \"Fetch warehouse details\"\n          hints:\n            readOnly: true\n          call: \"snowflake-warehouse.fetch-warehouse\"\n        - name: delete-warehouse\n          description: \"Delete a warehouse\"\n          hints:\n            destructive:\
  \ true\n          call: \"snowflake-warehouse.delete-warehouse\"\n        - name: list-compute-pools\n          description: \"List compute pools\"\n          hints:\n            readOnly: true\n          call: \"snowflake-compute-pool.list-compute-pools\"\n        - name: create-compute-pool\n          description: \"Create a compute pool\"\n          hints:\n            readOnly: false\n          call: \"snowflake-compute-pool.create-compute-pool\"\n        - name: list-services\n          description: \"List container services\"\n          hints:\n            readOnly: true\n          call: \"snowflake-service.list-services\"\n        - name: create-service\n          description: \"Create a container service\"\n          hints:\n            readOnly: false\n          call: \"snowflake-service.create-service\"\n        - name: fetch-service-status\n          description: \"Get service status\"\n          hints:\n            readOnly: true\n          call: \"snowflake-service.fetch-service-status\"\
  \n        - name: fetch-service-logs\n          description: \"Get service logs\"\n          hints:\n            readOnly: true\n          call: \"snowflake-service.fetch-service-logs\"\n        - name: resume-service\n          description: \"Resume a suspended service\"\n          hints:\n            readOnly: false\n          call: \"snowflake-service.resume-service\"\n        - name: suspend-service\n          description: \"Suspend a running service\"\n          hints:\n            readOnly: false\n          call: \"snowflake-service.suspend-service\"\n        - name: list-image-repositories\n          description: \"List image repositories\"\n          hints:\n            readOnly: true\n          call: \"snowflake-image-repository.list-image-repositories\"\n        - name: create-image-repository\n          description: \"Create an image repository\"\n          hints:\n            readOnly: false\n          call: \"snowflake-image-repository.create-image-repository\"\n        -\
  \ name: list-alerts\n          description: \"List monitoring alerts\"\n          hints:\n            readOnly: true\n          call: \"snowflake-alert.list-alerts\"\n        - name: create-alert\n          description: \"Create a monitoring alert\"\n          hints:\n            readOnly: false\n          call: \"snowflake-alert.create-alert\"\n        - name: execute-alert\n          description: \"Execute an alert\"\n          hints:\n            readOnly: false\n          call: \"snowflake-alert.execute-alert\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/compute-and-services.yaml
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
