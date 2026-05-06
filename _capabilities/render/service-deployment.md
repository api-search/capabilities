---
categories: []
consumed_apis: []
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
- delete a service
- restart a postgresql database instance
- create key value
- create a new project
- delete a render service
- manage deploys for a service
- list all render projects
- list services
- cloud
- get logs
- get service details
- list postgres
- get memory usage metrics for render services
- hosting
- get cpu usage metrics for render services
- trigger deploy
- list projects
- list infrastructure-as-code blueprints on render
- scale a render service to a specific number of instances
- resume a suspended service
- list postgresql database instances on render
- list env groups
- create postgres
- update configuration of a render service
- trigger a new deployment for a render service
- infrastructure
- list key value
- update service
- roll back a render service to a previous deployment
- update a service configuration
- restart a running service
- get cpu metrics
- scale a service to a specified number of instances
- list all projects
- create an environment group
- create service
- get service
- get details for a specific render service
- list postgresql instances
- restart postgres
- list deploy history for a render service
- create a key-value store instance
- retrieve logs for render services and resources
- infrastructure-as-code blueprints
- list all services on the render account
- resume service
- scale service
- service and resource logs
- resume a suspended render service
- suspend a running service
- devops
- shared environment variable groups
- projects and environments
- create a new managed postgresql database on render
- restart a service
- suspend a running render service to stop billing
- get memory metrics
- list deploys
- create project
- list deploy history for a service
- list blueprints
- get cpu usage metrics
- suspend service
- suspend a service
- restart a running render service
- create a new key-value (redis-compatible) store on render
- create env group
- scale a service
- databases
- list environment groups
- get, update, or delete a specific service
- deployment
- list all services
- list all blueprints
- create a new render project
- managed key-value (redis-compatible) stores
- restart service
- managed postgresql databases
- cpu performance metrics
- create a postgresql instance
- create a new render service
- rollback service
- retrieve logs for services
- list key-value store instances
- create a new render service (web service, background worker, etc.)
- platform
- web services
- trigger a new deploy
- list key-value store instances on render
- delete service
- list shared environment variable groups
- manage render web services, background workers, and private services
slug: service-deployment
source_filename: service-deployment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Render Service Deployment\n  description: 'Unified workflow for managing the full lifecycle of Render services: deploying web services and background\n    workers, managing PostgreSQL and Key-Value databases, configuring environments and blueprints, monitoring logs and metrics,\n    and scaling infrastructure. Used by platform engineers and DevOps teams automating cloud deployments on Render.'\n  tags:\n  - Cloud\n  - Deployment\n  - DevOps\n  - Infrastructure\n  - Platform\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RENDER_API_KEY: RENDER_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: render\n    baseUri: https://api.render.com/v1\n    description: Render Public API for managing cloud services and infrastructure\n    authentication:\n      type: bearer\n      token: '{{RENDER_API_KEY}}'\n    resources:\n    - name: services\n      path: /services\n      description: Web\
  \ services, static sites, background workers, and private services\n      operations:\n      - name: list-services\n        method: GET\n        description: List all services in the account\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Cursor for pagination\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by service type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-service\n        method: POST\n        description: Create a new service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \      body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            name: '{{tools.name}}'\n            ownerId: '{{tools.ownerId}}'\n      - name: get-service\n        method: GET\n        description: Get details of a specific service\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n          description: The service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-service\n        method: PATCH\n        description: Update a service configuration\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n          description: The service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n       \
  \   data:\n            name: '{{tools.name}}'\n      - name: delete-service\n        method: DELETE\n        description: Delete a service\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n          description: The service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suspend-service\n        method: POST\n        description: Suspend a running service\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n          description: The service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resume-service\n        method: POST\n        description: Resume a suspended service\n        inputParameters:\n        - name: serviceId\n          in: path\n      \
  \    type: string\n          required: true\n          description: The service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restart-service\n        method: POST\n        description: Restart a running service\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n          description: The service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: scale-service\n        method: POST\n        description: Scale a service to a specific number of instances\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n          description: The service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n        body:\n          type: json\n          data:\n            numInstances: '{{tools.numInstances}}'\n    - name: deploys\n      path: /services/{serviceId}/deploys\n      description: Service deployments and rollbacks\n      operations:\n      - name: list-deploys\n        method: GET\n        description: List deploys for a service\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n          description: The service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: trigger-deploy\n        method: POST\n        description: Trigger a new deploy for a service\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n          description: The service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n        body:\n          type: json\n          data:\n            clearCache: '{{tools.clearCache}}'\n      - name: rollback-service\n        method: POST\n        description: Rollback a service to a previous deploy\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n          description: The service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: postgres\n      path: /postgres\n      description: PostgreSQL managed database instances\n      operations:\n      - name: list-postgres\n        method: GET\n        description: List PostgreSQL database instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-postgres\n        method: POST\n        description: Create a new PostgreSQL\
  \ instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            ownerId: '{{tools.ownerId}}'\n            plan: '{{tools.plan}}'\n      - name: get-postgres\n        method: GET\n        description: Get details of a PostgreSQL instance\n        inputParameters:\n        - name: postgresId\n          in: path\n          type: string\n          required: true\n          description: The PostgreSQL instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: restart-postgres\n        method: POST\n        description: Restart a PostgreSQL instance\n        inputParameters:\n        - name: postgresId\n          in: path\n          type: string\n          required: true\n          description: The PostgreSQL instance ID\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: key-value\n      path: /key-value\n      description: Redis-compatible Key-Value store instances\n      operations:\n      - name: list-key-value\n        method: GET\n        description: List Key-Value store instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-key-value\n        method: POST\n        description: Create a new Key-Value store instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            ownerId: '{{tools.ownerId}}'\n            plan: '{{tools.plan}}'\n    - name: blueprints\n      path: /blueprints\n      description: Infrastructure-as-code blueprints via\
  \ render.yaml\n      operations:\n      - name: list-blueprints\n        method: GET\n        description: List all blueprints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: sync-blueprint\n        method: GET\n        description: Get blueprint sync history\n        inputParameters:\n        - name: blueprintId\n          in: path\n          type: string\n          required: true\n          description: The blueprint ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: env-groups\n      path: /env-groups\n      description: Shared environment variable groups\n      operations:\n      - name: list-env-groups\n        method: GET\n        description: List environment variable groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n\
  \      - name: create-env-group\n        method: POST\n        description: Create an environment variable group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            ownerId: '{{tools.ownerId}}'\n    - name: logs\n      path: /logs\n      description: Service and resource logs\n      operations:\n      - name: get-logs\n        method: GET\n        description: Retrieve logs for services and resources\n        inputParameters:\n        - name: serviceId\n          in: query\n          type: string\n          required: false\n          description: Filter logs by service ID\n        - name: startTime\n          in: query\n          type: string\n          required: false\n          description: Start time for log range\n        - name: endTime\n          in: query\n          type: string\n          required: false\n\
  \          description: End time for log range\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics/cpu\n      description: Service performance metrics\n      operations:\n      - name: get-cpu-metrics\n        method: GET\n        description: Get CPU usage metrics\n        inputParameters:\n        - name: serviceId\n          in: query\n          type: string\n          required: false\n          description: Filter by service ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-memory-metrics\n        method: GET\n        description: Get memory usage metrics\n        inputParameters:\n        - name: serviceId\n          in: query\n          type: string\n          required: false\n          description: Filter by service ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: Project and environment organization\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            ownerId: '{{tools.ownerId}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: render-deployment-api\n    description: Unified REST API for Render service deployment and management.\n    resources:\n    - path: /v1/services\n      name: services\n      description:\
  \ Manage Render web services, background workers, and private services\n      operations:\n      - method: GET\n        name: list-services\n        description: List all services\n        call: render.list-services\n        with:\n          cursor: rest.cursor\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-service\n        description: Create a new Render service\n        call: render.create-service\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceId}\n      name: service\n      description: Get, update, or delete a specific service\n      operations:\n      - method: GET\n        name: get-service\n        description: Get service details\n        call: render.get-service\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name:\
  \ update-service\n        description: Update a service configuration\n        call: render.update-service\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-service\n        description: Delete a service\n        call: render.delete-service\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceId}/deploys\n      name: deploys\n      description: Manage deploys for a service\n      operations:\n      - method: GET\n        name: list-deploys\n        description: List deploy history for a service\n        call: render.list-deploys\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: trigger-deploy\n        description: Trigger a new deploy\n        call: render.trigger-deploy\n\
  \        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceId}/suspend\n      name: service-suspend\n      description: Suspend a service\n      operations:\n      - method: POST\n        name: suspend-service\n        description: Suspend a running service\n        call: render.suspend-service\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceId}/resume\n      name: service-resume\n      description: Resume a suspended service\n      operations:\n      - method: POST\n        name: resume-service\n        description: Resume a suspended service\n        call: render.resume-service\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceId}/restart\n      name: service-restart\n\
  \      description: Restart a service\n      operations:\n      - method: POST\n        name: restart-service\n        description: Restart a running service\n        call: render.restart-service\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceId}/scale\n      name: service-scale\n      description: Scale a service\n      operations:\n      - method: POST\n        name: scale-service\n        description: Scale a service to a specified number of instances\n        call: render.scale-service\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/postgres\n      name: postgres\n      description: Managed PostgreSQL databases\n      operations:\n      - method: GET\n        name: list-postgres\n        description: List PostgreSQL instances\n        call: render.list-postgres\n        outputParameters:\n\
  \        - type: array\n          mapping: $.\n      - method: POST\n        name: create-postgres\n        description: Create a PostgreSQL instance\n        call: render.create-postgres\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/key-value\n      name: key-value\n      description: Managed Key-Value (Redis-compatible) stores\n      operations:\n      - method: GET\n        name: list-key-value\n        description: List Key-Value store instances\n        call: render.list-key-value\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-key-value\n        description: Create a Key-Value store instance\n        call: render.create-key-value\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/blueprints\n      name: blueprints\n      description: Infrastructure-as-code blueprints\n      operations:\n      - method: GET\n        name: list-blueprints\n\
  \        description: List all blueprints\n        call: render.list-blueprints\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/env-groups\n      name: env-groups\n      description: Shared environment variable groups\n      operations:\n      - method: GET\n        name: list-env-groups\n        description: List environment groups\n        call: render.list-env-groups\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-env-group\n        description: Create an environment group\n        call: render.create-env-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/logs\n      name: logs\n      description: Service and resource logs\n      operations:\n      - method: GET\n        name: get-logs\n        description: Retrieve logs for services\n        call: render.get-logs\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/metrics/cpu\n      name: metrics-cpu\n      description: CPU performance metrics\n      operations:\n      - method: GET\n        name: get-cpu-metrics\n        description: Get CPU usage metrics\n        call: render.get-cpu-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: Projects and environments\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all projects\n        call: render.list-projects\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new project\n        call: render.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: render-deployment-mcp\n    transport: http\n    description: MCP\
  \ server for AI-assisted Render service management and deployment automation.\n    tools:\n    - name: list-services\n      description: List all services on the Render account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: render.list-services\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-service\n      description: Get details for a specific Render service\n      hints:\n        readOnly: true\n        openWorld: false\n      call: render.get-service\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-service\n      description: Create a new Render service (web service, background worker, etc.)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: render.create-service\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: update-service\n      description: Update configuration of a Render service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: render.update-service\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-service\n      description: Delete a Render service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: render.delete-service\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trigger-deploy\n      description: Trigger a new deployment for a Render service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: render.trigger-deploy\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rollback-service\n\
  \      description: Roll back a Render service to a previous deployment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: render.rollback-service\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deploys\n      description: List deploy history for a Render service\n      hints:\n        readOnly: true\n        openWorld: true\n      call: render.list-deploys\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: suspend-service\n      description: Suspend a running Render service to stop billing\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: render.suspend-service\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resume-service\n      description:\
  \ Resume a suspended Render service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: render.resume-service\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restart-service\n      description: Restart a running Render service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: render.restart-service\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scale-service\n      description: Scale a Render service to a specific number of instances\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: render.scale-service\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-logs\n      description:\
  \ Retrieve logs for Render services and resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: render.get-logs\n      with:\n        serviceId: tools.serviceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cpu-metrics\n      description: Get CPU usage metrics for Render services\n      hints:\n        readOnly: true\n        openWorld: true\n      call: render.get-cpu-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-memory-metrics\n      description: Get memory usage metrics for Render services\n      hints:\n        readOnly: true\n        openWorld: true\n      call: render.get-memory-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-postgres\n      description: List PostgreSQL database instances on Render\n      hints:\n        readOnly: true\n        openWorld: true\n      call: render.list-postgres\n      outputParameters:\n\
  \      - type: array\n        mapping: $.\n    - name: create-postgres\n      description: Create a new managed PostgreSQL database on Render\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: render.create-postgres\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restart-postgres\n      description: Restart a PostgreSQL database instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: render.restart-postgres\n      with:\n        postgresId: tools.postgresId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-key-value\n      description: List Key-Value store instances on Render\n      hints:\n        readOnly: true\n        openWorld: true\n      call: render.list-key-value\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-key-value\n      description: Create a new Key-Value\
  \ (Redis-compatible) store on Render\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: render.create-key-value\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-blueprints\n      description: List infrastructure-as-code blueprints on Render\n      hints:\n        readOnly: true\n        openWorld: true\n      call: render.list-blueprints\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-env-groups\n      description: List shared environment variable groups\n      hints:\n        readOnly: true\n        openWorld: true\n      call: render.list-env-groups\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-projects\n      description: List all Render projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: render.list-projects\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name:\
  \ create-project\n      description: Create a new Render project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: render.create-project\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
