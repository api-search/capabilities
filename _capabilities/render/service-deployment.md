---
categories: []
consumed_apis:
- render
description: 'Unified workflow for managing the full lifecycle of Render services: deploying web services and background workers, managing PostgreSQL and Key-Value databases, configuring environments and blueprints, monitoring logs and metrics, and scaling infrastructure. Used by platform engineers and DevOps teams automating cloud deployments on Render.'
layout: capability
name: Render Service Deployment
operations:
- description: List all services
  method: GET
  name: list-services
  path: /v1/services
- description: Create a new Render service
  method: POST
  name: create-service
  path: /v1/services
- description: Get service details
  method: GET
  name: get-service
  path: /v1/services/{serviceId}
- description: Update a service configuration
  method: PATCH
  name: update-service
  path: /v1/services/{serviceId}
- description: Delete a service
  method: DELETE
  name: delete-service
  path: /v1/services/{serviceId}
- description: List deploy history for a service
  method: GET
  name: list-deploys
  path: /v1/services/{serviceId}/deploys
- description: Trigger a new deploy
  method: POST
  name: trigger-deploy
  path: /v1/services/{serviceId}/deploys
- description: Suspend a running service
  method: POST
  name: suspend-service
  path: /v1/services/{serviceId}/suspend
- description: Resume a suspended service
  method: POST
  name: resume-service
  path: /v1/services/{serviceId}/resume
- description: Restart a running service
  method: POST
  name: restart-service
  path: /v1/services/{serviceId}/restart
- description: Scale a service to a specified number of instances
  method: POST
  name: scale-service
  path: /v1/services/{serviceId}/scale
- description: List PostgreSQL instances
  method: GET
  name: list-postgres
  path: /v1/postgres
- description: Create a PostgreSQL instance
  method: POST
  name: create-postgres
  path: /v1/postgres
- description: List Key-Value store instances
  method: GET
  name: list-key-value
  path: /v1/key-value
- description: Create a Key-Value store instance
  method: POST
  name: create-key-value
  path: /v1/key-value
- description: List all blueprints
  method: GET
  name: list-blueprints
  path: /v1/blueprints
- description: List environment groups
  method: GET
  name: list-env-groups
  path: /v1/env-groups
- description: Create an environment group
  method: POST
  name: create-env-group
  path: /v1/env-groups
- description: Retrieve logs for services
  method: GET
  name: get-logs
  path: /v1/logs
- description: Get CPU usage metrics
  method: GET
  name: get-cpu-metrics
  path: /v1/metrics/cpu
- description: List all projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new project
  method: POST
  name: create-project
  path: /v1/projects
personas: []
provider_name: Render
provider_slug: render
search_terms:
- list services
- trigger deploy
- create a new render project
- list shared environment variable groups
- update service
- hosting
- list key-value store instances on render
- roll back a render service to a previous deployment
- resume service
- manage render web services, background workers, and private services
- manage deploys for a service
- scale service
- retrieve logs for services
- rollback service
- create a new project
- resume a suspended render service
- web services
- infrastructure-as-code blueprints
- suspend a running render service to stop billing
- create a new render service (web service, background worker, etc.)
- get cpu metrics
- get service details
- create an environment group
- list deploy history for a service
- restart a running service
- restart a service
- restart a running render service
- projects and environments
- list key-value store instances
- trigger a new deployment for a render service
- create service
- get memory usage metrics for render services
- list all render projects
- get cpu usage metrics for render services
- restart a postgresql database instance
- managed key-value (redis-compatible) stores
- scale a render service to a specific number of instances
- cpu performance metrics
- service and resource logs
- deployment
- devops
- infrastructure
- list blueprints
- delete service
- create a new managed postgresql database on render
- list all projects
- create a postgresql instance
- create a key-value store instance
- databases
- list postgresql instances
- scale a service
- get cpu usage metrics
- create key value
- get memory metrics
- restart service
- delete a service
- shared environment variable groups
- list all blueprints
- list env groups
- delete a render service
- list environment groups
- list postgres
- create a new key-value (redis-compatible) store on render
- suspend service
- update a service configuration
- update configuration of a render service
- get logs
- list postgresql database instances on render
- list projects
- suspend a running service
- trigger a new deploy
- list all services on the render account
- list deploy history for a render service
- managed postgresql databases
- create project
- restart postgres
- list all services
- get, update, or delete a specific service
- get details for a specific render service
- cloud
- create a new render service
- retrieve logs for render services and resources
- list deploys
- get service
- platform
- create env group
- suspend a service
- scale a service to a specified number of instances
- create postgres
- resume a suspended service
- list infrastructure-as-code blueprints on render
- list key value
slug: service-deployment
source_filename: service-deployment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Render Service Deployment\"\n  description: >-\n    Unified workflow for managing the full lifecycle of Render services: deploying\n    web services and background workers, managing PostgreSQL and Key-Value databases,\n    configuring environments and blueprints, monitoring logs and metrics, and\n    scaling infrastructure. Used by platform engineers and DevOps teams automating\n    cloud deployments on Render.\n  tags:\n    - Cloud\n    - Deployment\n    - DevOps\n    - Infrastructure\n    - Platform\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RENDER_API_KEY: RENDER_API_KEY\n\ncapability:\n  consumes:\n    - import: render\n      location: ./shared/render-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: render-deployment-api\n      description: \"Unified REST API for Render service deployment and management.\"\n      resources:\n        - path:\
  \ /v1/services\n          name: services\n          description: \"Manage Render web services, background workers, and private services\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List all services\"\n              call: \"render.list-services\"\n              with:\n                cursor: \"rest.cursor\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-service\n              description: \"Create a new Render service\"\n              call: \"render.create-service\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/{serviceId}\n          name: service\n          description: \"Get, update, or delete a specific service\"\n          operations:\n            - method: GET\n              name:\
  \ get-service\n              description: \"Get service details\"\n              call: \"render.get-service\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-service\n              description: \"Update a service configuration\"\n              call: \"render.update-service\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-service\n              description: \"Delete a service\"\n              call: \"render.delete-service\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/{serviceId}/deploys\n\
  \          name: deploys\n          description: \"Manage deploys for a service\"\n          operations:\n            - method: GET\n              name: list-deploys\n              description: \"List deploy history for a service\"\n              call: \"render.list-deploys\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: trigger-deploy\n              description: \"Trigger a new deploy\"\n              call: \"render.trigger-deploy\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/{serviceId}/suspend\n          name: service-suspend\n          description: \"Suspend a service\"\n          operations:\n            - method: POST\n              name: suspend-service\n   \
  \           description: \"Suspend a running service\"\n              call: \"render.suspend-service\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/{serviceId}/resume\n          name: service-resume\n          description: \"Resume a suspended service\"\n          operations:\n            - method: POST\n              name: resume-service\n              description: \"Resume a suspended service\"\n              call: \"render.resume-service\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/{serviceId}/restart\n          name: service-restart\n          description: \"Restart a service\"\n          operations:\n            - method: POST\n              name: restart-service\n         \
  \     description: \"Restart a running service\"\n              call: \"render.restart-service\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/{serviceId}/scale\n          name: service-scale\n          description: \"Scale a service\"\n          operations:\n            - method: POST\n              name: scale-service\n              description: \"Scale a service to a specified number of instances\"\n              call: \"render.scale-service\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/postgres\n          name: postgres\n          description: \"Managed PostgreSQL databases\"\n          operations:\n            - method: GET\n              name: list-postgres\n              description:\
  \ \"List PostgreSQL instances\"\n              call: \"render.list-postgres\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-postgres\n              description: \"Create a PostgreSQL instance\"\n              call: \"render.create-postgres\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/key-value\n          name: key-value\n          description: \"Managed Key-Value (Redis-compatible) stores\"\n          operations:\n            - method: GET\n              name: list-key-value\n              description: \"List Key-Value store instances\"\n              call: \"render.list-key-value\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-key-value\n              description: \"Create a Key-Value store instance\"\
  \n              call: \"render.create-key-value\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/blueprints\n          name: blueprints\n          description: \"Infrastructure-as-code blueprints\"\n          operations:\n            - method: GET\n              name: list-blueprints\n              description: \"List all blueprints\"\n              call: \"render.list-blueprints\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/env-groups\n          name: env-groups\n          description: \"Shared environment variable groups\"\n          operations:\n            - method: GET\n              name: list-env-groups\n              description: \"List environment groups\"\n              call: \"render.list-env-groups\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n\
  \              name: create-env-group\n              description: \"Create an environment group\"\n              call: \"render.create-env-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/logs\n          name: logs\n          description: \"Service and resource logs\"\n          operations:\n            - method: GET\n              name: get-logs\n              description: \"Retrieve logs for services\"\n              call: \"render.get-logs\"\n              with:\n                serviceId: \"rest.serviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metrics/cpu\n          name: metrics-cpu\n          description: \"CPU performance metrics\"\n          operations:\n            - method: GET\n              name: get-cpu-metrics\n              description: \"Get CPU usage metrics\"\n              call: \"render.get-cpu-metrics\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects\n          name: projects\n          description: \"Projects and environments\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all projects\"\n              call: \"render.list-projects\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create a new project\"\n              call: \"render.create-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: render-deployment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Render service management and deployment automation.\"\n      tools:\n        - name: list-services\n\
  \          description: \"List all services on the Render account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"render.list-services\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-service\n          description: \"Get details for a specific Render service\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"render.get-service\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-service\n          description: \"Create a new Render service (web service, background worker, etc.)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"render.create-service\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: update-service\n          description: \"Update configuration of a Render service\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"render.update-service\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-service\n          description: \"Delete a Render service\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"render.delete-service\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: trigger-deploy\n          description: \"Trigger a new deployment for a Render service\"\n          hints:\n            readOnly: false\n\
  \            destructive: false\n            idempotent: false\n          call: \"render.trigger-deploy\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: rollback-service\n          description: \"Roll back a Render service to a previous deployment\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"render.rollback-service\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-deploys\n          description: \"List deploy history for a Render service\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"render.list-deploys\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: array\n\
  \              mapping: \"$.\"\n        - name: suspend-service\n          description: \"Suspend a running Render service to stop billing\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"render.suspend-service\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: resume-service\n          description: \"Resume a suspended Render service\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"render.resume-service\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: restart-service\n          description: \"Restart a running Render service\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: false\n          call: \"render.restart-service\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: scale-service\n          description: \"Scale a Render service to a specific number of instances\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"render.scale-service\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-logs\n          description: \"Retrieve logs for Render services and resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"render.get-logs\"\n          with:\n            serviceId: \"tools.serviceId\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: get-cpu-metrics\n          description: \"Get CPU usage metrics for Render services\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"render.get-cpu-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-memory-metrics\n          description: \"Get memory usage metrics for Render services\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"render.get-memory-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-postgres\n          description: \"List PostgreSQL database instances on Render\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"render.list-postgres\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-postgres\n          description:\
  \ \"Create a new managed PostgreSQL database on Render\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"render.create-postgres\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: restart-postgres\n          description: \"Restart a PostgreSQL database instance\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"render.restart-postgres\"\n          with:\n            postgresId: \"tools.postgresId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-key-value\n          description: \"List Key-Value store instances on Render\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"render.list-key-value\"\n          outputParameters:\n            - type: array\n              mapping:\
  \ \"$.\"\n        - name: create-key-value\n          description: \"Create a new Key-Value (Redis-compatible) store on Render\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"render.create-key-value\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-blueprints\n          description: \"List infrastructure-as-code blueprints on Render\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"render.list-blueprints\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-env-groups\n          description: \"List shared environment variable groups\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"render.list-env-groups\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n   \
  \     - name: list-projects\n          description: \"List all Render projects\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"render.list-projects\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-project\n          description: \"Create a new Render project\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"render.create-project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/render/refs/heads/main/capabilities/service-deployment.yaml
tags:
- Cloud
- Deployment
- DevOps
- Infrastructure
- Platform
tools:
- description: List all services on the Render account
  hints:
    openWorld: true
    readOnly: true
  name: list-services
- description: Get details for a specific Render service
  hints:
    openWorld: false
    readOnly: true
  name: get-service
- description: Create a new Render service (web service, background worker, etc.)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-service
- description: Update configuration of a Render service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-service
- description: Delete a Render service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-service
- description: Trigger a new deployment for a Render service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: trigger-deploy
- description: Roll back a Render service to a previous deployment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rollback-service
- description: List deploy history for a Render service
  hints:
    openWorld: true
    readOnly: true
  name: list-deploys
- description: Suspend a running Render service to stop billing
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: suspend-service
- description: Resume a suspended Render service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resume-service
- description: Restart a running Render service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restart-service
- description: Scale a Render service to a specific number of instances
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: scale-service
- description: Retrieve logs for Render services and resources
  hints:
    openWorld: true
    readOnly: true
  name: get-logs
- description: Get CPU usage metrics for Render services
  hints:
    openWorld: true
    readOnly: true
  name: get-cpu-metrics
- description: Get memory usage metrics for Render services
  hints:
    openWorld: true
    readOnly: true
  name: get-memory-metrics
- description: List PostgreSQL database instances on Render
  hints:
    openWorld: true
    readOnly: true
  name: list-postgres
- description: Create a new managed PostgreSQL database on Render
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-postgres
- description: Restart a PostgreSQL database instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restart-postgres
- description: List Key-Value store instances on Render
  hints:
    openWorld: true
    readOnly: true
  name: list-key-value
- description: Create a new Key-Value (Redis-compatible) store on Render
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-key-value
- description: List infrastructure-as-code blueprints on Render
  hints:
    openWorld: true
    readOnly: true
  name: list-blueprints
- description: List shared environment variable groups
  hints:
    openWorld: true
    readOnly: true
  name: list-env-groups
- description: List all Render projects
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Create a new Render project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-project
---
