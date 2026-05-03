---
categories: []
consumed_apis:
- extend
- orchestration
- custom-objects
description: Unified capability for building, deploying, and managing custom Workday Extend applications. Combines app lifecycle management, orchestration automation, and custom object data modeling into a single developer workflow.
layout: capability
name: Workday Extend App Development
operations:
- description: List all Extend applications
  method: GET
  name: list-apps
  path: /v1/apps
- description: Register a new Extend application
  method: POST
  name: create-app
  path: /v1/apps
- description: Retrieve an Extend application
  method: GET
  name: get-app
  path: /v1/apps/{appId}
- description: Update an Extend application
  method: PATCH
  name: update-app
  path: /v1/apps/{appId}
- description: Delete an Extend application
  method: DELETE
  name: delete-app
  path: /v1/apps/{appId}
- description: List application versions
  method: GET
  name: list-app-versions
  path: /v1/apps/{appId}/versions
- description: Create a new application version
  method: POST
  name: create-app-version
  path: /v1/apps/{appId}/versions
- description: List application deployments
  method: GET
  name: list-app-deployments
  path: /v1/apps/{appId}/deployments
- description: Deploy an Extend application
  method: POST
  name: deploy-app
  path: /v1/apps/{appId}/deployments
- description: List application configurations
  method: GET
  name: list-app-configurations
  path: /v1/apps/{appId}/configurations
- description: Update application configurations
  method: PUT
  name: update-app-configurations
  path: /v1/apps/{appId}/configurations
- description: List orchestrations
  method: GET
  name: list-orchestrations
  path: /v1/orchestrations
- description: Create an orchestration
  method: POST
  name: create-orchestration
  path: /v1/orchestrations
- description: List orchestration executions
  method: GET
  name: list-executions
  path: /v1/orchestrations/{orchestrationId}/executions
- description: Launch an orchestration execution
  method: POST
  name: launch-execution
  path: /v1/orchestrations/{orchestrationId}/executions
- description: List custom object definitions
  method: GET
  name: list-custom-object-definitions
  path: /v1/custom-object-definitions
- description: Retrieve custom object data for a worker
  method: GET
  name: get-worker-custom-object-data
  path: /v1/workers/{workerId}/custom-objects/{objectType}
- description: Create or update custom object data for a worker
  method: PUT
  name: upsert-worker-custom-object-data
  path: /v1/workers/{workerId}/custom-objects/{objectType}
personas: []
provider_name: Workday Extend
provider_slug: workday-extend
search_terms:
- list app deployments
- create app version
- create or update custom object data for a worker
- list all extend applications
- list application deployments
- list apps
- retrieve custom object data for a worker
- register a new workday extend custom application
- update metadata or configuration of an extend application
- list all versions of an extend application
- automation
- update configuration settings for an extend application
- deploy an extend application version to sandbox or production
- register a new extend application
- list all orchestration definitions in the tenant
- workday
- manage a specific extend application
- create a new application version
- custom object data for workers
- create app
- create orchestration
- get worker custom object data
- get details of a specific extend application including status and version
- retrieve custom object data attached to a worker record
- manage business process orchestrations
- hcm
- launch execution
- list application configurations
- delete app
- update application configurations
- launch a new orchestration execution with input data
- integration
- retrieve an extend application
- manage application versions
- get app
- update app
- list app versions
- extensions
- platform development
- custom object type definitions
- enterprise
- list app configurations
- update app configurations
- list application versions
- create an orchestration
- upsert worker custom object data
- create a new business process orchestration
- list executions
- launch an orchestration execution
- list custom object definitions
- list orchestration executions
- list orchestrations
- list deployment history for an extend application
- delete an extend application
- deploy an extend application
- list all custom object type definitions in the tenant
- deploy app
- paas
- manage application deployments
- custom objects
- remove an extend application from the tenant
- manage application configuration settings
- manage extend application registrations
- list executions for a specific orchestration
- list all extend applications registered in the workday tenant
- orchestration
- orchestration execution management
- create a new version of an extend application
- update an extend application
- extend
- human capital management
- list configuration settings for an extend application
- custom applications
slug: app-development
source_filename: app-development.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Extend App Development\"\n  description: \"Unified capability for building, deploying, and managing custom Workday Extend applications. Combines app lifecycle management, orchestration automation, and custom object data modeling into a single developer workflow.\"\n  tags:\n    - Workday\n    - Extend\n    - Custom Applications\n    - Orchestration\n    - Custom Objects\n    - Platform Development\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_EXTEND_ACCESS_TOKEN: WORKDAY_EXTEND_ACCESS_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - import: extend\n      location: ./shared/extend-rest-api.yaml\n    - import: orchestration\n      location: ./shared/orchestration.yaml\n    - import: custom-objects\n      location: ./shared/custom-objects.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workday-extend-api\n\
  \      description: \"Unified REST API for Workday Extend app development lifecycle.\"\n      resources:\n        - path: /v1/apps\n          name: apps\n          description: \"Manage Extend application registrations\"\n          operations:\n            - method: GET\n              name: list-apps\n              description: \"List all Extend applications\"\n              call: \"extend.list-apps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-app\n              description: \"Register a new Extend application\"\n              call: \"extend.create-app\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apps/{appId}\n          name: app-detail\n          description: \"Manage a specific Extend application\"\n          operations:\n            - method: GET\n              name: get-app\n              description:\
  \ \"Retrieve an Extend application\"\n              call: \"extend.get-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-app\n              description: \"Update an Extend application\"\n              call: \"extend.update-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-app\n              description: \"Delete an Extend application\"\n              call: \"extend.delete-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apps/{appId}/versions\n          name: app-versions\n          description: \"Manage application\
  \ versions\"\n          operations:\n            - method: GET\n              name: list-app-versions\n              description: \"List application versions\"\n              call: \"extend.list-app-versions\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-app-version\n              description: \"Create a new application version\"\n              call: \"extend.create-app-version\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apps/{appId}/deployments\n          name: app-deployments\n          description: \"Manage application deployments\"\n          operations:\n            - method: GET\n              name: list-app-deployments\n              description: \"List application deployments\"\
  \n              call: \"extend.list-app-deployments\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: deploy-app\n              description: \"Deploy an Extend application\"\n              call: \"extend.deploy-app\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apps/{appId}/configurations\n          name: app-configurations\n          description: \"Manage application configuration settings\"\n          operations:\n            - method: GET\n              name: list-app-configurations\n              description: \"List application configurations\"\n              call: \"extend.list-app-configurations\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-app-configurations\n              description: \"Update application configurations\"\n              call: \"extend.update-app-configurations\"\n              with:\n                appId: \"rest.appId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orchestrations\n          name: orchestrations\n          description: \"Manage business process orchestrations\"\n          operations:\n            - method: GET\n              name: list-orchestrations\n              description: \"List orchestrations\"\n              call: \"orchestration.list-orchestrations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-orchestration\n              description: \"Create an orchestration\"\n          \
  \    call: \"orchestration.create-orchestration\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orchestrations/{orchestrationId}/executions\n          name: orchestration-executions\n          description: \"Orchestration execution management\"\n          operations:\n            - method: GET\n              name: list-executions\n              description: \"List orchestration executions\"\n              call: \"orchestration.list-executions\"\n              with:\n                orchestrationId: \"rest.orchestrationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: launch-execution\n              description: \"Launch an orchestration execution\"\n              call: \"orchestration.launch-execution\"\n              with:\n                orchestrationId: \"rest.orchestrationId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/custom-object-definitions\n          name: custom-object-definitions\n          description: \"Custom object type definitions\"\n          operations:\n            - method: GET\n              name: list-custom-object-definitions\n              description: \"List custom object definitions\"\n              call: \"custom-objects.list-custom-object-definitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/custom-objects/{objectType}\n          name: worker-custom-objects\n          description: \"Custom object data for workers\"\n          operations:\n            - method: GET\n              name: get-worker-custom-object-data\n              description: \"Retrieve custom object data for a worker\"\n              call: \"custom-objects.get-worker-custom-object-data\"\n              with:\n               \
  \ workerId: \"rest.workerId\"\n                objectType: \"rest.objectType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: upsert-worker-custom-object-data\n              description: \"Create or update custom object data for a worker\"\n              call: \"custom-objects.upsert-worker-custom-object-data\"\n              with:\n                workerId: \"rest.workerId\"\n                objectType: \"rest.objectType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: workday-extend-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Workday Extend application development and orchestration.\"\n      tools:\n        - name: list-apps\n          description: \"List all Extend applications registered in the Workday tenant\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"extend.list-apps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-app\n          description: \"Register a new Workday Extend custom application\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"extend.create-app\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-app\n          description: \"Get details of a specific Extend application including status and version\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"extend.get-app\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-app\n          description: \"Update metadata or configuration of an Extend application\"\n          hints:\n            readOnly:\
  \ false\n            destructive: false\n            idempotent: true\n          call: \"extend.update-app\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-app\n          description: \"Remove an Extend application from the tenant\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"extend.delete-app\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-app-versions\n          description: \"List all versions of an Extend application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"extend.list-app-versions\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: create-app-version\n          description: \"Create a new version of an Extend application\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"extend.create-app-version\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-app-deployments\n          description: \"List deployment history for an Extend application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"extend.list-app-deployments\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deploy-app\n          description: \"Deploy an Extend application version to sandbox or production\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"extend.deploy-app\"\
  \n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-app-configurations\n          description: \"List configuration settings for an Extend application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"extend.list-app-configurations\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-app-configurations\n          description: \"Update configuration settings for an Extend application\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"extend.update-app-configurations\"\n          with:\n            appId: \"tools.appId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-orchestrations\n\
  \          description: \"List all orchestration definitions in the tenant\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"orchestration.list-orchestrations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-orchestration\n          description: \"Create a new business process orchestration\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"orchestration.create-orchestration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-executions\n          description: \"List executions for a specific orchestration\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"orchestration.list-executions\"\n          with:\n            orchestrationId: \"tools.orchestrationId\"\n          outputParameters:\n            - type: object\n        \
  \      mapping: \"$.\"\n        - name: launch-execution\n          description: \"Launch a new orchestration execution with input data\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"orchestration.launch-execution\"\n          with:\n            orchestrationId: \"tools.orchestrationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-custom-object-definitions\n          description: \"List all custom object type definitions in the tenant\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"custom-objects.list-custom-object-definitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-worker-custom-object-data\n          description: \"Retrieve custom object data attached to a worker record\"\n          hints:\n            readOnly: true\n            openWorld: true\n  \
  \        call: \"custom-objects.get-worker-custom-object-data\"\n          with:\n            workerId: \"tools.workerId\"\n            objectType: \"tools.objectType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: upsert-worker-custom-object-data\n          description: \"Create or update custom object data for a worker\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"custom-objects.upsert-worker-custom-object-data\"\n          with:\n            workerId: \"tools.workerId\"\n            objectType: \"tools.objectType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-extend/refs/heads/main/capabilities/app-development.yaml
tags:
- Workday
- Extend
- Custom Applications
- Orchestration
- Custom Objects
- Platform Development
tools:
- description: List all Extend applications registered in the Workday tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-apps
- description: Register a new Workday Extend custom application
  hints:
    destructive: false
    readOnly: false
  name: create-app
- description: Get details of a specific Extend application including status and version
  hints:
    openWorld: true
    readOnly: true
  name: get-app
- description: Update metadata or configuration of an Extend application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-app
- description: Remove an Extend application from the tenant
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-app
- description: List all versions of an Extend application
  hints:
    openWorld: true
    readOnly: true
  name: list-app-versions
- description: Create a new version of an Extend application
  hints:
    destructive: false
    readOnly: false
  name: create-app-version
- description: List deployment history for an Extend application
  hints:
    openWorld: true
    readOnly: true
  name: list-app-deployments
- description: Deploy an Extend application version to sandbox or production
  hints:
    destructive: false
    readOnly: false
  name: deploy-app
- description: List configuration settings for an Extend application
  hints:
    openWorld: true
    readOnly: true
  name: list-app-configurations
- description: Update configuration settings for an Extend application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-app-configurations
- description: List all orchestration definitions in the tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-orchestrations
- description: Create a new business process orchestration
  hints:
    destructive: false
    readOnly: false
  name: create-orchestration
- description: List executions for a specific orchestration
  hints:
    openWorld: true
    readOnly: true
  name: list-executions
- description: Launch a new orchestration execution with input data
  hints:
    destructive: false
    readOnly: false
  name: launch-execution
- description: List all custom object type definitions in the tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-custom-object-definitions
- description: Retrieve custom object data attached to a worker record
  hints:
    openWorld: true
    readOnly: true
  name: get-worker-custom-object-data
- description: Create or update custom object data for a worker
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: upsert-worker-custom-object-data
---
