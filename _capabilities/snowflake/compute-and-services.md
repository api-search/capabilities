---
api_specs:
- filename: warehouse.yaml
  format: yaml
  label: snowflake-warehouse
  slug: snowflake-warehouse
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/warehouse.yaml
- filename: compute-pool.yaml
  format: yaml
  label: snowflake-compute-pool
  slug: snowflake-compute-pool
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/compute-pool.yaml
- filename: service.yaml
  format: yaml
  label: snowflake-service
  slug: snowflake-service
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/service.yaml
- filename: image-repository.yaml
  format: yaml
  label: snowflake-image-repository
  slug: snowflake-image-repository
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/image-repository.yaml
- filename: alert.yaml
  format: yaml
  label: snowflake-alert
  slug: snowflake-alert
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/alert.yaml
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
- list services
- warehouse management
- compute pool management
- list container services
- fetch service status
- execute alert
- suspend a running service
- data warehousing
- list monitoring alerts
- snowflake
- list image repositories
- data lakes
- create an alert
- create a warehouse
- alert management
- container service management
- delete a warehouse
- resume service
- list alerts
- delete warehouse
- create image repository
- list warehouses
- create warehouse
- create alert
- create a virtual warehouse
- create service
- create compute pool
- create an image repository
- get service status
- fetch warehouse
- database
- fetch service logs
- fetch warehouse details
- create a monitoring alert
- containers
- sql
- data sharing
- compute
- list virtual warehouses
- create a container service
- create a compute pool
- infrastructure
- create a service
- execute an alert
- list compute pools
- resume a suspended service
- suspend service
- get service logs
slug: compute-and-services
source_filename: compute-and-services.yaml
source_heading: Capability Spec
source_yaml: "# This capability composes the imported shared Snowflake capabilities\n# (warehouse, compute-pool, service, image-repository, alert) and exposes\n# them uniformly across MCP (http + stdio), Agent Skills, and REST — so one\n# integration layer serves remote MCP agents, local IDE agents, skill hosts,\n# and conventional REST clients.\nnaftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowflake Compute and Services\"\n  description: \"Unified workflow for managing warehouses, compute pools, Snowpark Container Services, image repositories, and monitoring alerts. Used by Platform Engineers and DevOps teams to provision and operate compute infrastructure.\"\n  tags:\n    - Snowflake\n    - Compute\n    - Containers\n    - Infrastructure\n  created: \"2026-04-18\"\n  modified: \"2026-04-23\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n      SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: snowflake-warehouse\n\
  \      location: ./shared/warehouse.yaml\n    - import: snowflake-compute-pool\n      location: ./shared/compute-pool.yaml\n    - import: snowflake-service\n      location: ./shared/service.yaml\n    - import: snowflake-image-repository\n      location: ./shared/image-repository.yaml\n    - import: snowflake-alert\n      location: ./shared/alert.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: snowflake-compute-api\n      description: \"Unified REST API for Snowflake compute and services management.\"\n      resources:\n        - path: /v1/warehouses\n          name: warehouses\n          description: \"Warehouse management\"\n          operations:\n            - method: GET\n              name: list-warehouses\n              description: \"List warehouses\"\n              call: \"snowflake-warehouse.list-warehouses\"\n              inputParameters:\n                - name: like\n                  type: string\n                  description: \"Optional LIKE pattern\
  \ to filter warehouse names.\"\n                  required: false\n                  mapping: \"queryParameters.like\"\n              outputParameters:\n                - name: warehouses\n                  type: array\n                  mapping: \"$[*]\"\n                - name: count\n                  type: integer\n                  mapping: \"$.length\"\n            - method: POST\n              name: create-warehouse\n              description: \"Create a warehouse\"\n              call: \"snowflake-warehouse.create-warehouse\"\n              inputParameters:\n                - name: name\n                  type: string\n                  description: \"Warehouse name.\"\n                  required: true\n                  mapping: \"body.name\"\n                - name: warehouse_size\n                  type: string\n                  description: \"Warehouse size (e.g. XSMALL, SMALL, MEDIUM).\"\n                  required: false\n                  mapping: \"body.warehouse_size\"\
  \n                - name: auto_suspend\n                  type: integer\n                  description: \"Auto-suspend idle timeout in seconds.\"\n                  required: false\n                  mapping: \"body.auto_suspend\"\n              outputParameters:\n                - name: name\n                  type: string\n                  mapping: \"$.name\"\n                - name: state\n                  type: string\n                  mapping: \"$.state\"\n        - path: /v1/compute-pools\n          name: compute-pools\n          description: \"Compute pool management\"\n          operations:\n            - method: GET\n              name: list-compute-pools\n              description: \"List compute pools\"\n              call: \"snowflake-compute-pool.list-compute-pools\"\n              inputParameters:\n                - name: like\n                  type: string\n                  description: \"Optional LIKE pattern to filter compute pool names.\"\n                  required:\
  \ false\n                  mapping: \"queryParameters.like\"\n              outputParameters:\n                - name: compute_pools\n                  type: array\n                  mapping: \"$[*]\"\n                - name: count\n                  type: integer\n                  mapping: \"$.length\"\n            - method: POST\n              name: create-compute-pool\n              description: \"Create a compute pool\"\n              call: \"snowflake-compute-pool.create-compute-pool\"\n              inputParameters:\n                - name: name\n                  type: string\n                  description: \"Compute pool name.\"\n                  required: true\n                  mapping: \"body.name\"\n                - name: instance_family\n                  type: string\n                  description: \"Instance family (e.g. CPU_X64_XS).\"\n                  required: true\n                  mapping: \"body.instance_family\"\n                - name: min_nodes\n          \
  \        type: integer\n                  description: \"Minimum node count.\"\n                  required: true\n                  mapping: \"body.min_nodes\"\n                - name: max_nodes\n                  type: integer\n                  description: \"Maximum node count.\"\n                  required: true\n                  mapping: \"body.max_nodes\"\n              outputParameters:\n                - name: name\n                  type: string\n                  mapping: \"$.name\"\n                - name: state\n                  type: string\n                  mapping: \"$.state\"\n        - path: /v1/services\n          name: services\n          description: \"Container service management\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List services\"\n              call: \"snowflake-service.list-services\"\n              inputParameters:\n                - name: database\n                  type: string\n\
  \                  description: \"Target database name.\"\n                  required: true\n                  mapping: \"pathParameters.database\"\n                - name: schema\n                  type: string\n                  description: \"Target schema name.\"\n                  required: true\n                  mapping: \"pathParameters.schema\"\n              outputParameters:\n                - name: services\n                  type: array\n                  mapping: \"$[*]\"\n                - name: count\n                  type: integer\n                  mapping: \"$.length\"\n            - method: POST\n              name: create-service\n              description: \"Create a service\"\n              call: \"snowflake-service.create-service\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Target database name.\"\n                  required: true\n                  mapping: \"pathParameters.database\"\
  \n                - name: schema\n                  type: string\n                  description: \"Target schema name.\"\n                  required: true\n                  mapping: \"pathParameters.schema\"\n                - name: name\n                  type: string\n                  description: \"Service name.\"\n                  required: true\n                  mapping: \"body.name\"\n                - name: compute_pool\n                  type: string\n                  description: \"Compute pool name that runs the service.\"\n                  required: true\n                  mapping: \"body.compute_pool\"\n                - name: spec\n                  type: object\n                  description: \"Service specification (image, endpoints, env).\"\n                  required: true\n                  mapping: \"body.spec\"\n              outputParameters:\n                - name: name\n                  type: string\n                  mapping: \"$.name\"\n               \
  \ - name: status\n                  type: string\n                  mapping: \"$.status\"\n        - path: /v1/alerts\n          name: alerts\n          description: \"Alert management\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description: \"List alerts\"\n              call: \"snowflake-alert.list-alerts\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Target database name.\"\n                  required: true\n                  mapping: \"pathParameters.database\"\n                - name: schema\n                  type: string\n                  description: \"Target schema name.\"\n                  required: true\n                  mapping: \"pathParameters.schema\"\n              outputParameters:\n                - name: alerts\n                  type: array\n                  mapping: \"$[*]\"\n                - name: count\n             \
  \     type: integer\n                  mapping: \"$.length\"\n            - method: POST\n              name: create-alert\n              description: \"Create an alert\"\n              call: \"snowflake-alert.create-alert\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Target database name.\"\n                  required: true\n                  mapping: \"pathParameters.database\"\n                - name: schema\n                  type: string\n                  description: \"Target schema name.\"\n                  required: true\n                  mapping: \"pathParameters.schema\"\n                - name: name\n                  type: string\n                  description: \"Alert name.\"\n                  required: true\n                  mapping: \"body.name\"\n                - name: condition\n                  type: string\n                  description: \"SQL condition that triggers the alert.\"\
  \n                  required: true\n                  mapping: \"body.condition\"\n                - name: action\n                  type: string\n                  description: \"Action to execute when the condition is met.\"\n                  required: true\n                  mapping: \"body.action\"\n              outputParameters:\n                - name: name\n                  type: string\n                  mapping: \"$.name\"\n                - name: state\n                  type: string\n                  mapping: \"$.state\"\n\n    - type: mcp\n      port: 9084\n      namespace: snowflake-compute-mcp\n      transport: http\n      description: \"MCP server (Streaming HTTP) for AI-assisted Snowflake compute and services management.\"\n      tools:\n        - name: list-warehouses\n          description: \"List virtual warehouses\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-warehouse.list-warehouses\"\
  \n          inputParameters:\n            - name: like\n              type: string\n              description: \"Optional LIKE pattern to filter warehouse names.\"\n              required: false\n              mapping: \"queryParameters.like\"\n          outputParameters:\n            - name: warehouses\n              type: array\n              mapping: \"$[*]\"\n            - name: count\n              type: integer\n              mapping: \"$.length\"\n        - name: create-warehouse\n          description: \"Create a virtual warehouse\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-warehouse.create-warehouse\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Warehouse name.\"\n              required: true\n              mapping: \"body.name\"\n            - name: warehouse_size\n              type: string\n              description:\
  \ \"Warehouse size (e.g. XSMALL, SMALL, MEDIUM).\"\n              required: false\n              mapping: \"body.warehouse_size\"\n            - name: auto_suspend\n              type: integer\n              description: \"Auto-suspend idle timeout in seconds.\"\n              required: false\n              mapping: \"body.auto_suspend\"\n          outputParameters:\n            - name: name\n              type: string\n              mapping: \"$.name\"\n            - name: state\n              type: string\n              mapping: \"$.state\"\n        - name: fetch-warehouse\n          description: \"Fetch warehouse details\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-warehouse.fetch-warehouse\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Warehouse name to fetch.\"\n              required: true\n              mapping: \"pathParameters.name\"\
  \n          outputParameters:\n            - name: name\n              type: string\n              mapping: \"$.name\"\n            - name: size\n              type: string\n              mapping: \"$.warehouse_size\"\n            - name: state\n              type: string\n              mapping: \"$.state\"\n            - name: auto_suspend\n              type: integer\n              mapping: \"$.auto_suspend\"\n        - name: delete-warehouse\n          description: \"Delete a warehouse\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"snowflake-warehouse.delete-warehouse\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Warehouse name to delete.\"\n              required: true\n              mapping: \"pathParameters.name\"\n          outputParameters:\n            - name: status\n              type: string\n              mapping: \"$.status\"\
  \n        - name: list-compute-pools\n          description: \"List compute pools\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-compute-pool.list-compute-pools\"\n          inputParameters:\n            - name: like\n              type: string\n              description: \"Optional LIKE pattern to filter compute pool names.\"\n              required: false\n              mapping: \"queryParameters.like\"\n          outputParameters:\n            - name: compute_pools\n              type: array\n              mapping: \"$[*]\"\n            - name: count\n              type: integer\n              mapping: \"$.length\"\n        - name: create-compute-pool\n          description: \"Create a compute pool\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-compute-pool.create-compute-pool\"\n          inputParameters:\n\
  \            - name: name\n              type: string\n              description: \"Compute pool name.\"\n              required: true\n              mapping: \"body.name\"\n            - name: instance_family\n              type: string\n              description: \"Instance family (e.g. CPU_X64_XS).\"\n              required: true\n              mapping: \"body.instance_family\"\n            - name: min_nodes\n              type: integer\n              description: \"Minimum node count.\"\n              required: true\n              mapping: \"body.min_nodes\"\n            - name: max_nodes\n              type: integer\n              description: \"Maximum node count.\"\n              required: true\n              mapping: \"body.max_nodes\"\n          outputParameters:\n            - name: name\n              type: string\n              mapping: \"$.name\"\n            - name: state\n              type: string\n              mapping: \"$.state\"\n        - name: list-services\n    \
  \      description: \"List container services\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-service.list-services\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n              description: \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\n          outputParameters:\n            - name: services\n              type: array\n              mapping: \"$[*]\"\n            - name: count\n              type: integer\n              mapping: \"$.length\"\n        - name: create-service\n          description: \"Create a container service\"\n          hints:\n            readOnly: false\n            destructive: false\n \
  \           idempotent: false\n          call: \"snowflake-service.create-service\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n              description: \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\n            - name: name\n              type: string\n              description: \"Service name.\"\n              required: true\n              mapping: \"body.name\"\n            - name: compute_pool\n              type: string\n              description: \"Compute pool that runs the service.\"\n              required: true\n              mapping: \"body.compute_pool\"\n            - name: spec\n              type: object\n              description: \"Service specification (image, endpoints, env).\"\
  \n              required: true\n              mapping: \"body.spec\"\n          outputParameters:\n            - name: name\n              type: string\n              mapping: \"$.name\"\n            - name: status\n              type: string\n              mapping: \"$.status\"\n        - name: fetch-service-status\n          description: \"Get service status\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-service.fetch-service-status\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n              description: \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\n            - name: name\n              type: string\n \
  \             description: \"Service name.\"\n              required: true\n              mapping: \"pathParameters.name\"\n          outputParameters:\n            - name: status\n              type: string\n              mapping: \"$.status\"\n            - name: message\n              type: string\n              mapping: \"$.message\"\n        - name: fetch-service-logs\n          description: \"Get service logs\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-service.fetch-service-logs\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n              description: \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\n \
  \           - name: name\n              type: string\n              description: \"Service name.\"\n              required: true\n              mapping: \"pathParameters.name\"\n            - name: instance_id\n              type: string\n              description: \"Instance identifier within the service.\"\n              required: false\n              mapping: \"queryParameters.instanceId\"\n          outputParameters:\n            - name: logs\n              type: string\n              mapping: \"$.logs\"\n        - name: resume-service\n          description: \"Resume a suspended service\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"snowflake-service.resume-service\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            -\
  \ name: schema\n              type: string\n              description: \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\n            - name: name\n              type: string\n              description: \"Service name.\"\n              required: true\n              mapping: \"pathParameters.name\"\n          outputParameters:\n            - name: status\n              type: string\n              mapping: \"$.status\"\n        - name: suspend-service\n          description: \"Suspend a running service\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"snowflake-service.suspend-service\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n\
  \              description: \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\n            - name: name\n              type: string\n              description: \"Service name.\"\n              required: true\n              mapping: \"pathParameters.name\"\n          outputParameters:\n            - name: status\n              type: string\n              mapping: \"$.status\"\n        - name: list-image-repositories\n          description: \"List image repositories\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-image-repository.list-image-repositories\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n              description:\
  \ \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\n          outputParameters:\n            - name: image_repositories\n              type: array\n              mapping: \"$[*]\"\n            - name: count\n              type: integer\n              mapping: \"$.length\"\n        - name: create-image-repository\n          description: \"Create an image repository\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-image-repository.create-image-repository\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n              description: \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\
  \n            - name: name\n              type: string\n              description: \"Image repository name.\"\n              required: true\n              mapping: \"body.name\"\n          outputParameters:\n            - name: name\n              type: string\n              mapping: \"$.name\"\n            - name: repository_url\n              type: string\n              mapping: \"$.repository_url\"\n        - name: list-alerts\n          description: \"List monitoring alerts\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-alert.list-alerts\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n              description: \"Target schema name.\"\n              required: true\n\
  \              mapping: \"pathParameters.schema\"\n          outputParameters:\n            - name: alerts\n              type: array\n              mapping: \"$[*]\"\n            - name: count\n              type: integer\n              mapping: \"$.length\"\n        - name: create-alert\n          description: \"Create a monitoring alert\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-alert.create-alert\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n              description: \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\n            - name: name\n              type: string\n              description: \"Alert\
  \ name.\"\n              required: true\n              mapping: \"body.name\"\n            - name: condition\n              type: string\n              description: \"SQL condition that triggers the alert.\"\n              required: true\n              mapping: \"body.condition\"\n            - name: action\n              type: string\n              description: \"Action to execute when the condition is met.\"\n              required: true\n              mapping: \"body.action\"\n          outputParameters:\n            - name: name\n              type: string\n              mapping: \"$.name\"\n            - name: state\n              type: string\n              mapping: \"$.state\"\n        - name: execute-alert\n          description: \"Execute an alert\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-alert.execute-alert\"\n          inputParameters:\n            - name: database\n          \
  \    type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n              description: \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\n            - name: name\n              type: string\n              description: \"Alert name to execute.\"\n              required: true\n              mapping: \"pathParameters.name\"\n          outputParameters:\n            - name: status\n              type: string\n              mapping: \"$.status\"\n\n    - type: mcp\n      port: 9085\n      namespace: snowflake-compute-mcp-stdio\n      transport: stdio\n      description: \"MCP server (Standard IO) for local IDE/agent hosts.\"\n      tools:\n        - name: list-warehouses\n          description: \"List virtual warehouses\"\n          hints:\n            readOnly: true\n            destructive:\
  \ false\n            idempotent: true\n          call: \"snowflake-warehouse.list-warehouses\"\n          inputParameters:\n            - name: like\n              type: string\n              description: \"Optional LIKE pattern to filter warehouse names.\"\n              required: false\n              mapping: \"queryParameters.like\"\n          outputParameters:\n            - name: warehouses\n              type: array\n              mapping: \"$[*]\"\n            - name: count\n              type: integer\n              mapping: \"$.length\"\n        - name: create-warehouse\n          description: \"Create a virtual warehouse\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-warehouse.create-warehouse\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Warehouse name.\"\n              required: true\n              mapping: \"body.name\"\
  \n            - name: warehouse_size\n              type: string\n              description: \"Warehouse size (e.g. XSMALL, SMALL, MEDIUM).\"\n              required: false\n              mapping: \"body.warehouse_size\"\n            - name: auto_suspend\n              type: integer\n              description: \"Auto-suspend idle timeout in seconds.\"\n              required: false\n              mapping: \"body.auto_suspend\"\n          outputParameters:\n            - name: name\n              type: string\n              mapping: \"$.name\"\n            - name: state\n              type: string\n              mapping: \"$.state\"\n        - name: fetch-warehouse\n          description: \"Fetch warehouse details\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-warehouse.fetch-warehouse\"\n          inputParameters:\n            - name: name\n              type: string\n              description:\
  \ \"Warehouse name to fetch.\"\n              required: true\n              mapping: \"pathParameters.name\"\n          outputParameters:\n            - name: name\n              type: string\n              mapping: \"$.name\"\n            - name: size\n              type: string\n              mapping: \"$.warehouse_size\"\n            - name: state\n              type: string\n              mapping: \"$.state\"\n            - name: auto_suspend\n              type: integer\n              mapping: \"$.auto_suspend\"\n        - name: delete-warehouse\n          description: \"Delete a warehouse\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"snowflake-warehouse.delete-warehouse\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Warehouse name to delete.\"\n              required: true\n              mapping: \"pathParameters.name\"\n          outputParameters:\n\
  \            - name: status\n              type: string\n              mapping: \"$.status\"\n        - name: list-compute-pools\n          description: \"List compute pools\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-compute-pool.list-compute-pools\"\n          inputParameters:\n            - name: like\n              type: string\n              description: \"Optional LIKE pattern to filter compute pool names.\"\n              required: false\n              mapping: \"queryParameters.like\"\n          outputParameters:\n            - name: compute_pools\n              type: array\n              mapping: \"$[*]\"\n            - name: count\n              type: integer\n              mapping: \"$.length\"\n        - name: create-compute-pool\n          description: \"Create a compute pool\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent:\
  \ false\n          call: \"snowflake-compute-pool.create-compute-pool\"\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Compute pool name.\"\n              required: true\n              mapping: \"body.name\"\n            - name: instance_family\n              type: string\n              description: \"Instance family (e.g. CPU_X64_XS).\"\n              required: true\n              mapping: \"body.instance_family\"\n            - name: min_nodes\n              type: integer\n              description: \"Minimum node count.\"\n              required: true\n              mapping: \"body.min_nodes\"\n            - name: max_nodes\n              type: integer\n              description: \"Maximum node count.\"\n              required: true\n              mapping: \"body.max_nodes\"\n          outputParameters:\n            - name: name\n              type: string\n              mapping: \"$.name\"\n            - name: state\n\
  \              type: string\n              mapping: \"$.state\"\n        - name: list-services\n          description: \"List container services\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-service.list-services\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Target database name.\"\n              required: true\n              mapping: \"pathParameters.database\"\n            - name: schema\n              type: string\n              description: \"Target schema name.\"\n              required: true\n              mapping: \"pathParameters.schema\"\n          outputParameters:\n            - name: services\n              type: array\n              mapping: \"$[*]\"\n            - name: count\n              type: integer\n              mapping: \"$.length\"\n        - name: create-service\n          description: \"Create a container\
  \ service\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-service.create-service\"\n          inputParameters:\n    \n\n# --- truncated at 32 KB (57 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/compute-and-services.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/compute-and-services.yaml
tags:
- Snowflake
- Compute
- Containers
- Infrastructure
tools:
- description: List virtual warehouses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-warehouses
- description: Create a virtual warehouse
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-warehouse
- description: Fetch warehouse details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-warehouse
- description: Delete a warehouse
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-warehouse
- description: List compute pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-compute-pools
- description: Create a compute pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-compute-pool
- description: List container services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-services
- description: Create a container service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-service
- description: Get service status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-service-status
- description: Get service logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-service-logs
- description: Resume a suspended service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resume-service
- description: Suspend a running service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: suspend-service
- description: List image repositories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-image-repositories
- description: Create an image repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-image-repository
- description: List monitoring alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-alerts
- description: Create a monitoring alert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-alert
- description: Execute an alert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-alert
- description: List virtual warehouses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-warehouses
- description: Create a virtual warehouse
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-warehouse
- description: Fetch warehouse details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-warehouse
- description: Delete a warehouse
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-warehouse
- description: List compute pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-compute-pools
- description: Create a compute pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-compute-pool
- description: List container services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-services
- description: Create a container service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-service
- description: Get service status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-service-status
- description: Get service logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-service-logs
- description: Resume a suspended service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resume-service
- description: Suspend a running service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: suspend-service
- description: List image repositories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-image-repositories
- description: Create an image repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-image-repository
- description: List monitoring alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-alerts
- description: Create a monitoring alert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-alert
- description: Execute an alert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-alert
---
