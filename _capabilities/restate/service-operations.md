---
categories: []
consumed_apis: []
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
- kill invocation
- get service metadata and handlers
- purge completed invocations
- service registry and metadata
- distributed systems
- services
- get metadata and handler list for a specific restate service
- list all kafka subscriptions
- durable execution
- list all registered service deployments
- get deployment
- cluster health and version
- remove a service deployment from restate
- delete deployment
- create a kafka subscription
- list all restate service deployments registered with the cluster
- get details and services of a specific restate deployment
- cancel an in-flight restate invocation by id
- create a kafka subscription to trigger restate handlers on incoming messages
- forcefully kill an invocation
- deployments
- delete a deployment
- create subscription
- register a new service endpoint with restate so it can receive invocations
- list services
- register a new service deployment
- modify service
- list deployments
- individual service management
- cancel an in-flight invocation
- operations
- invocations
- get deployment details
- list subscriptions
- purge a completed restate invocation and free its associated state
- list service handlers
- force kill a restate invocation (immediate termination)
- get cluster health status
- orchestration
- list all registered services
- get service
- force kill invocations
- workflows
- register and manage service deployments
- list all kafka subscriptions configured in restate
- list all services registered in restate
- cancel active invocations
- list all durable handlers for a restate service
- create deployment
- modify service configuration
- purge invocation
- register deployment
- purge a completed invocation
- individual deployment management
- list all handlers for a service
- update restate service configuration such as public access
- kafka subscriptions for event-driven invocations
- kafka
- check the health status of the restate cluster
- microservices
- service handler inspection
- cluster health
- cancel invocation
slug: service-operations
source_filename: service-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Restate Service Operations\n  description: Unified capability for managing the full lifecycle of Restate services and deployments. Covers registering\n    service deployments, inspecting service metadata and handlers, managing in-flight invocations, and configuring Kafka subscriptions\n    for event-driven execution.\n  tags:\n  - Durable Execution\n  - Deployments\n  - Services\n  - Invocations\n  - Kafka\n  - Operations\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RESTATE_ADMIN_URL: RESTATE_ADMIN_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: restate-admin\n    baseUri: http://localhost:9070\n    description: Restate Admin API for cluster and service management\n    resources:\n    - name: deployments\n      path: /deployments\n      description: Service deployment registration and management\n      operations:\n      - name: list-deployments\n        method: GET\n        description:\
  \ List all registered service deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Register a new service deployment with Restate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            uri: '{{tools.uri}}'\n            force: '{{tools.force}}'\n            dry_run: '{{tools.dry_run}}'\n      - name: get-deployment\n        method: GET\n        description: Get details of a specific deployment\n        inputParameters:\n        - name: deployment\n          in: path\n          type: string\n          required: true\n          description: The deployment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: delete-deployment\n        method: DELETE\n        description: Delete a service deployment\n        inputParameters:\n        - name: deployment\n          in: path\n          type: string\n          required: true\n          description: The deployment identifier\n        - name: force\n          in: query\n          type: boolean\n          required: false\n          description: Force deletion even if active invocations exist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /services\n      description: Service metadata and configuration management\n      operations:\n      - name: list-services\n        method: GET\n        description: List all registered services and their handlers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-service\n        method: GET\n\
  \        description: Get metadata for a specific service\n        inputParameters:\n        - name: service\n          in: path\n          type: string\n          required: true\n          description: The service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modify-service\n        method: PATCH\n        description: Modify service configuration (public access, retention policies)\n        inputParameters:\n        - name: service\n          in: path\n          type: string\n          required: true\n          description: The service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            public: '{{tools.public}}'\n      - name: list-service-handlers\n        method: GET\n        description: List all handlers for a service\n        inputParameters:\n\
  \        - name: service\n          in: path\n          type: string\n          required: true\n          description: The service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-service-handler\n        method: GET\n        description: Get metadata for a specific service handler\n        inputParameters:\n        - name: service\n          in: path\n          type: string\n          required: true\n          description: The service name\n        - name: handler\n          in: path\n          type: string\n          required: true\n          description: The handler name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invocations\n      path: /invocations\n      description: In-flight invocation management\n      operations:\n      - name: cancel-invocation\n        method: PATCH\n        description:\
  \ Cancel an in-flight invocation\n        inputParameters:\n        - name: invocation_id\n          in: path\n          type: string\n          required: true\n          description: The invocation identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: kill-invocation\n        method: PATCH\n        description: Forcefully kill an invocation\n        inputParameters:\n        - name: invocation_id\n          in: path\n          type: string\n          required: true\n          description: The invocation identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: purge-invocation\n        method: PATCH\n        description: Purge a completed invocation and its state\n        inputParameters:\n        - name: invocation_id\n          in: path\n          type: string\n          required: true\n    \
  \      description: The invocation identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /subscriptions\n      description: Kafka subscription management for event-driven invocations\n      operations:\n      - name: list-subscriptions\n        method: GET\n        description: List all Kafka subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-subscription\n        method: POST\n        description: Create a new Kafka subscription to trigger service handlers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            source: '{{tools.source}}'\n            sink: '{{tools.sink}}'\n      - name: get-subscription\n        method:\
  \ GET\n        description: Get details of a specific Kafka subscription\n        inputParameters:\n        - name: subscription\n          in: path\n          type: string\n          required: true\n          description: The subscription identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-subscription\n        method: DELETE\n        description: Delete a Kafka subscription\n        inputParameters:\n        - name: subscription\n          in: path\n          type: string\n          required: true\n          description: The subscription identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-health\n      path: /cluster-health\n      description: Cluster health and version information\n      operations:\n      - name: cluster-health\n        method: GET\n        description:\
  \ Get the health status of the Restate cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-version\n        method: GET\n        description: Get Restate Admin API version information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: restate-operations-api\n    description: Unified REST API for Restate service operations, invocation management, and Kafka subscriptions.\n    resources:\n    - path: /v1/deployments\n      name: deployments\n      description: Register and manage service deployments\n      operations:\n      - method: GET\n        name: list-deployments\n        description: List all registered service deployments\n        call: restate-admin.list-deployments\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \   - method: POST\n        name: create-deployment\n        description: Register a new service deployment\n        call: restate-admin.create-deployment\n        with:\n          uri: rest.body.uri\n          force: rest.body.force\n          dry_run: rest.body.dry_run\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments/{deployment}\n      name: deployment\n      description: Individual deployment management\n      operations:\n      - method: GET\n        name: get-deployment\n        description: Get deployment details\n        call: restate-admin.get-deployment\n        with:\n          deployment: rest.deployment\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-deployment\n        description: Delete a deployment\n        call: restate-admin.delete-deployment\n        with:\n          deployment: rest.deployment\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/services\n      name: services\n      description: Service registry and metadata\n      operations:\n      - method: GET\n        name: list-services\n        description: List all registered services\n        call: restate-admin.list-services\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{service}\n      name: service\n      description: Individual service management\n      operations:\n      - method: GET\n        name: get-service\n        description: Get service metadata and handlers\n        call: restate-admin.get-service\n        with:\n          service: rest.service\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: modify-service\n        description: Modify service configuration\n        call: restate-admin.modify-service\n        with:\n          service: rest.service\n          public: rest.body.public\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/services/{service}/handlers\n      name: service-handlers\n      description: Service handler inspection\n      operations:\n      - method: GET\n        name: list-service-handlers\n        description: List all handlers for a service\n        call: restate-admin.list-service-handlers\n        with:\n          service: rest.service\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invocations/{invocation_id}/cancel\n      name: invocation-cancel\n      description: Cancel active invocations\n      operations:\n      - method: PATCH\n        name: cancel-invocation\n        description: Cancel an in-flight invocation\n        call: restate-admin.cancel-invocation\n        with:\n          invocation_id: rest.invocation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invocations/{invocation_id}/kill\n      name: invocation-kill\n      description:\
  \ Force kill invocations\n      operations:\n      - method: PATCH\n        name: kill-invocation\n        description: Forcefully kill an invocation\n        call: restate-admin.kill-invocation\n        with:\n          invocation_id: rest.invocation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invocations/{invocation_id}/purge\n      name: invocation-purge\n      description: Purge completed invocations\n      operations:\n      - method: PATCH\n        name: purge-invocation\n        description: Purge a completed invocation\n        call: restate-admin.purge-invocation\n        with:\n          invocation_id: rest.invocation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions\n      name: subscriptions\n      description: Kafka subscriptions for event-driven invocations\n      operations:\n      - method: GET\n        name: list-subscriptions\n        description: List all Kafka\
  \ subscriptions\n        call: restate-admin.list-subscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-subscription\n        description: Create a Kafka subscription\n        call: restate-admin.create-subscription\n        with:\n          source: rest.body.source\n          sink: rest.body.sink\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cluster-health\n      name: cluster-health\n      description: Cluster health and version\n      operations:\n      - method: GET\n        name: cluster-health\n        description: Get cluster health status\n        call: restate-admin.cluster-health\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: restate-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted Restate service operations, deployment management, and invocation control.\n\
  \    tools:\n    - name: list-deployments\n      description: List all Restate service deployments registered with the cluster\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: restate-admin.list-deployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-deployment\n      description: Register a new service endpoint with Restate so it can receive invocations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: restate-admin.create-deployment\n      with:\n        uri: tools.uri\n        force: tools.force\n        dry_run: tools.dry_run\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployment\n      description: Get details and services of a specific Restate deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: restate-admin.get-deployment\n\
  \      with:\n        deployment: tools.deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-deployment\n      description: Remove a service deployment from Restate\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: restate-admin.delete-deployment\n      with:\n        deployment: tools.deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-services\n      description: List all services registered in Restate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: restate-admin.list-services\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-service\n      description: Get metadata and handler list for a specific Restate service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: restate-admin.get-service\n      with:\n\
  \        service: tools.service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modify-service\n      description: Update Restate service configuration such as public access\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: restate-admin.modify-service\n      with:\n        service: tools.service\n        public: tools.public\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-handlers\n      description: List all durable handlers for a Restate service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: restate-admin.list-service-handlers\n      with:\n        service: tools.service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-invocation\n      description: Cancel an in-flight Restate invocation by ID\n      hints:\n        readOnly: false\n        destructive: true\n\
  \        idempotent: true\n      call: restate-admin.cancel-invocation\n      with:\n        invocation_id: tools.invocation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: kill-invocation\n      description: Force kill a Restate invocation (immediate termination)\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: restate-admin.kill-invocation\n      with:\n        invocation_id: tools.invocation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: purge-invocation\n      description: Purge a completed Restate invocation and free its associated state\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: restate-admin.purge-invocation\n      with:\n        invocation_id: tools.invocation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subscriptions\n      description: List all\
  \ Kafka subscriptions configured in Restate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: restate-admin.list-subscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-subscription\n      description: Create a Kafka subscription to trigger Restate handlers on incoming messages\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: restate-admin.create-subscription\n      with:\n        source: tools.source\n        sink: tools.sink\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cluster-health\n      description: Check the health status of the Restate cluster\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: restate-admin.cluster-health\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
