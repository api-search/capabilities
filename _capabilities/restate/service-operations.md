---
categories: []
consumed_apis:
- restate-admin
description: Unified capability for managing the full lifecycle of Restate services and deployments. Covers registering service deployments, inspecting service metadata and handlers, managing in-flight invocations, and configuring Kafka subscriptions for event-driven execution.
layout: capability
name: Restate Service Operations
operations:
- description: List all registered service deployments
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: Register a new service deployment
  method: POST
  name: create-deployment
  path: /v1/deployments
- description: Get deployment details
  method: GET
  name: get-deployment
  path: /v1/deployments/{deployment}
- description: Delete a deployment
  method: DELETE
  name: delete-deployment
  path: /v1/deployments/{deployment}
- description: List all registered services
  method: GET
  name: list-services
  path: /v1/services
- description: Get service metadata and handlers
  method: GET
  name: get-service
  path: /v1/services/{service}
- description: Modify service configuration
  method: PATCH
  name: modify-service
  path: /v1/services/{service}
- description: List all handlers for a service
  method: GET
  name: list-service-handlers
  path: /v1/services/{service}/handlers
- description: Cancel an in-flight invocation
  method: PATCH
  name: cancel-invocation
  path: /v1/invocations/{invocation_id}/cancel
- description: Forcefully kill an invocation
  method: PATCH
  name: kill-invocation
  path: /v1/invocations/{invocation_id}/kill
- description: Purge a completed invocation
  method: PATCH
  name: purge-invocation
  path: /v1/invocations/{invocation_id}/purge
- description: List all Kafka subscriptions
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: Create a Kafka subscription
  method: POST
  name: create-subscription
  path: /v1/subscriptions
- description: Get cluster health status
  method: GET
  name: cluster-health
  path: /v1/cluster-health
personas: []
provider_name: Restate
provider_slug: restate
search_terms:
- list services
- get service metadata and handlers
- durable execution
- service handler inspection
- purge a completed invocation
- get deployment
- list all restate service deployments registered with the cluster
- cancel invocation
- list all registered services
- cancel an in-flight invocation
- get cluster health status
- list subscriptions
- list all services registered in restate
- create deployment
- list all handlers for a service
- kill invocation
- delete a deployment
- get details and services of a specific restate deployment
- service registry and metadata
- remove a service deployment from restate
- get deployment details
- operations
- individual service management
- deployments
- force kill a restate invocation (immediate termination)
- individual deployment management
- cluster health and version
- purge completed invocations
- check the health status of the restate cluster
- register deployment
- delete deployment
- cancel an in-flight restate invocation by id
- workflows
- create a kafka subscription
- create subscription
- kafka
- distributed systems
- list all registered service deployments
- cancel active invocations
- cluster health
- services
- modify service
- update restate service configuration such as public access
- force kill invocations
- get service
- list deployments
- microservices
- purge a completed restate invocation and free its associated state
- purge invocation
- list all kafka subscriptions configured in restate
- orchestration
- register a new service deployment
- register a new service endpoint with restate so it can receive invocations
- get metadata and handler list for a specific restate service
- list service handlers
- invocations
- modify service configuration
- kafka subscriptions for event-driven invocations
- register and manage service deployments
- list all durable handlers for a restate service
- create a kafka subscription to trigger restate handlers on incoming messages
- forcefully kill an invocation
- list all kafka subscriptions
slug: service-operations
source_filename: service-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Restate Service Operations\"\n  description: \"Unified capability for managing the full lifecycle of Restate services and deployments. Covers registering service deployments, inspecting service metadata and handlers, managing in-flight invocations, and configuring Kafka subscriptions for event-driven execution.\"\n  tags:\n    - Durable Execution\n    - Deployments\n    - Services\n    - Invocations\n    - Kafka\n    - Operations\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RESTATE_ADMIN_URL: RESTATE_ADMIN_URL\n\ncapability:\n  consumes:\n    - import: restate-admin\n      location: ./shared/restate-admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: restate-operations-api\n      description: \"Unified REST API for Restate service operations, invocation management, and Kafka subscriptions.\"\n      resources:\n        - path: /v1/deployments\n\
  \          name: deployments\n          description: \"Register and manage service deployments\"\n          operations:\n            - method: GET\n              name: list-deployments\n              description: \"List all registered service deployments\"\n              call: \"restate-admin.list-deployments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-deployment\n              description: \"Register a new service deployment\"\n              call: \"restate-admin.create-deployment\"\n              with:\n                uri: \"rest.body.uri\"\n                force: \"rest.body.force\"\n                dry_run: \"rest.body.dry_run\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/deployments/{deployment}\n          name: deployment\n          description: \"Individual deployment management\"\n       \
  \   operations:\n            - method: GET\n              name: get-deployment\n              description: \"Get deployment details\"\n              call: \"restate-admin.get-deployment\"\n              with:\n                deployment: \"rest.deployment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-deployment\n              description: \"Delete a deployment\"\n              call: \"restate-admin.delete-deployment\"\n              with:\n                deployment: \"rest.deployment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/services\n          name: services\n          description: \"Service registry and metadata\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List all registered services\"\n              call: \"restate-admin.list-services\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/services/{service}\n          name: service\n          description: \"Individual service management\"\n          operations:\n            - method: GET\n              name: get-service\n              description: \"Get service metadata and handlers\"\n              call: \"restate-admin.get-service\"\n              with:\n                service: \"rest.service\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: modify-service\n              description: \"Modify service configuration\"\n              call: \"restate-admin.modify-service\"\n              with:\n                service: \"rest.service\"\n                public: \"rest.body.public\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/services/{service}/handlers\n\
  \          name: service-handlers\n          description: \"Service handler inspection\"\n          operations:\n            - method: GET\n              name: list-service-handlers\n              description: \"List all handlers for a service\"\n              call: \"restate-admin.list-service-handlers\"\n              with:\n                service: \"rest.service\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invocations/{invocation_id}/cancel\n          name: invocation-cancel\n          description: \"Cancel active invocations\"\n          operations:\n            - method: PATCH\n              name: cancel-invocation\n              description: \"Cancel an in-flight invocation\"\n              call: \"restate-admin.cancel-invocation\"\n              with:\n                invocation_id: \"rest.invocation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/invocations/{invocation_id}/kill\n          name: invocation-kill\n          description: \"Force kill invocations\"\n          operations:\n            - method: PATCH\n              name: kill-invocation\n              description: \"Forcefully kill an invocation\"\n              call: \"restate-admin.kill-invocation\"\n              with:\n                invocation_id: \"rest.invocation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invocations/{invocation_id}/purge\n          name: invocation-purge\n          description: \"Purge completed invocations\"\n          operations:\n            - method: PATCH\n              name: purge-invocation\n              description: \"Purge a completed invocation\"\n              call: \"restate-admin.purge-invocation\"\n              with:\n                invocation_id: \"rest.invocation_id\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Kafka subscriptions for event-driven invocations\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List all Kafka subscriptions\"\n              call: \"restate-admin.list-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-subscription\n              description: \"Create a Kafka subscription\"\n              call: \"restate-admin.create-subscription\"\n              with:\n                source: \"rest.body.source\"\n                sink: \"rest.body.sink\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cluster-health\n          name: cluster-health\n          description: \"Cluster\
  \ health and version\"\n          operations:\n            - method: GET\n              name: cluster-health\n              description: \"Get cluster health status\"\n              call: \"restate-admin.cluster-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: restate-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Restate service operations, deployment management, and invocation control.\"\n      tools:\n        - name: list-deployments\n          description: \"List all Restate service deployments registered with the cluster\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"restate-admin.list-deployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: register-deployment\n          description: \"\
  Register a new service endpoint with Restate so it can receive invocations\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"restate-admin.create-deployment\"\n          with:\n            uri: \"tools.uri\"\n            force: \"tools.force\"\n            dry_run: \"tools.dry_run\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-deployment\n          description: \"Get details and services of a specific Restate deployment\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"restate-admin.get-deployment\"\n          with:\n            deployment: \"tools.deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-deployment\n          description: \"Remove a service deployment from Restate\"\n          hints:\n\
  \            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"restate-admin.delete-deployment\"\n          with:\n            deployment: \"tools.deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-services\n          description: \"List all services registered in Restate\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"restate-admin.list-services\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-service\n          description: \"Get metadata and handler list for a specific Restate service\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"restate-admin.get-service\"\n          with:\n            service: \"tools.service\"\n          outputParameters:\n \
  \           - type: object\n              mapping: \"$.\"\n        - name: modify-service\n          description: \"Update Restate service configuration such as public access\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"restate-admin.modify-service\"\n          with:\n            service: \"tools.service\"\n            public: \"tools.public\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-service-handlers\n          description: \"List all durable handlers for a Restate service\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"restate-admin.list-service-handlers\"\n          with:\n            service: \"tools.service\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-invocation\n          description:\
  \ \"Cancel an in-flight Restate invocation by ID\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"restate-admin.cancel-invocation\"\n          with:\n            invocation_id: \"tools.invocation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: kill-invocation\n          description: \"Force kill a Restate invocation (immediate termination)\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"restate-admin.kill-invocation\"\n          with:\n            invocation_id: \"tools.invocation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: purge-invocation\n          description: \"Purge a completed Restate invocation and free its associated state\"\n          hints:\n            readOnly: false\n            destructive:\
  \ true\n            idempotent: true\n          call: \"restate-admin.purge-invocation\"\n          with:\n            invocation_id: \"tools.invocation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subscriptions\n          description: \"List all Kafka subscriptions configured in Restate\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"restate-admin.list-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-subscription\n          description: \"Create a Kafka subscription to trigger Restate handlers on incoming messages\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"restate-admin.create-subscription\"\n          with:\n            source: \"tools.source\"\n            sink: \"tools.sink\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cluster-health\n          description: \"Check the health status of the Restate cluster\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"restate-admin.cluster-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/restate/refs/heads/main/capabilities/service-operations.yaml
tags:
- Durable Execution
- Deployments
- Services
- Invocations
- Kafka
- Operations
tools:
- description: List all Restate service deployments registered with the cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-deployments
- description: Register a new service endpoint with Restate so it can receive invocations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: register-deployment
- description: Get details and services of a specific Restate deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-deployment
- description: Remove a service deployment from Restate
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-deployment
- description: List all services registered in Restate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-services
- description: Get metadata and handler list for a specific Restate service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-service
- description: Update Restate service configuration such as public access
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: modify-service
- description: List all durable handlers for a Restate service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-service-handlers
- description: Cancel an in-flight Restate invocation by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-invocation
- description: Force kill a Restate invocation (immediate termination)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: kill-invocation
- description: Purge a completed Restate invocation and free its associated state
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: purge-invocation
- description: List all Kafka subscriptions configured in Restate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-subscriptions
- description: Create a Kafka subscription to trigger Restate handlers on incoming messages
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-subscription
- description: Check the health status of the Restate cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cluster-health
---
