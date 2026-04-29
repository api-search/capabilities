---
categories:
- container-orchestration
consumed_apis:
- ecs
description: Container orchestration workflow for DevOps engineers and platform teams to manage ECS clusters, deploy services, run tasks, and monitor container workloads.
layout: capability
name: Amazon ECS Container Orchestration
operations:
- description: List all ECS clusters.
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Create a new ECS cluster.
  method: POST
  name: create-cluster
  path: /v1/clusters
- description: List services in a cluster.
  method: GET
  name: list-services
  path: /v1/services
- description: Create a new service.
  method: POST
  name: create-service
  path: /v1/services
- description: List task definitions.
  method: GET
  name: list-task-definitions
  path: /v1/task-definitions
- description: Register a new task definition.
  method: POST
  name: register-task-definition
  path: /v1/task-definitions
- description: List tasks in a cluster.
  method: GET
  name: list-tasks
  path: /v1/tasks
- description: Run a new task.
  method: POST
  name: run-task
  path: /v1/tasks
personas: []
provider_name: Amazon ECS
provider_slug: amazon-ecs
search_terms:
- stop task
- describe one or more ecs clusters.
- list tasks
- delete an ecs cluster.
- describe one or more ecs services.
- orchestration
- describe a task definition.
- create a new service.
- list services in an ecs cluster.
- docker
- list task definitions
- delete cluster
- ecs
- run task
- list task definition families or revisions.
- execute command
- list clusters
- stop a running task.
- containers
- register a new task definition.
- ecs task definition management.
- list tasks in a cluster.
- delete service
- describe one or more tasks.
- deregister a task definition revision.
- update service
- amazon
- register task definition
- describe tasks
- describe clusters
- aws
- create cluster
- list task definitions.
- describe task definition
- list all ecs clusters in the account.
- list services
- delete an ecs service.
- deregister task definition
- create a new ecs cluster.
- list services in a cluster.
- describe services
- list all ecs clusters.
- execute a command in a running container.
- ecs cluster management.
- run a new task.
- create a new ecs service.
- ecs task execution.
- update an ecs service configuration.
- ecs service management.
- create service
- run a new task from a task definition.
slug: container-orchestration
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon ECS Container Orchestration\"\n  description: \"Container orchestration workflow for DevOps engineers and platform teams to manage ECS clusters, deploy services, run tasks, and monitor container workloads.\"\n  tags:\n    - Amazon\n    - Containers\n    - Orchestration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: ecs\n      location: ./shared/ecs.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: container-orchestration-api\n      description: \"Unified REST API for Amazon ECS container orchestration.\"\n      resources:\n        - path: /v1/clusters\n          name: clusters\n          description: \"ECS cluster management.\"\n          operations:\n            - method: GET\n     \
  \         name: list-clusters\n              description: \"List all ECS clusters.\"\n              call: \"ecs.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cluster\n              description: \"Create a new ECS cluster.\"\n              call: \"ecs.create-cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/services\n          name: services\n          description: \"ECS service management.\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List services in a cluster.\"\n              call: \"ecs.list-services\"\n              with:\n                cluster: \"rest.cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name:\
  \ create-service\n              description: \"Create a new service.\"\n              call: \"ecs.create-service\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/task-definitions\n          name: task-definitions\n          description: \"ECS task definition management.\"\n          operations:\n            - method: GET\n              name: list-task-definitions\n              description: \"List task definitions.\"\n              call: \"ecs.list-task-definitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: register-task-definition\n              description: \"Register a new task definition.\"\n              call: \"ecs.register-task-definition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tasks\n          name: tasks\n          description:\
  \ \"ECS task execution.\"\n          operations:\n            - method: GET\n              name: list-tasks\n              description: \"List tasks in a cluster.\"\n              call: \"ecs.list-tasks\"\n              with:\n                cluster: \"rest.cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: run-task\n              description: \"Run a new task.\"\n              call: \"ecs.run-task\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: container-orchestration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon ECS container orchestration.\"\n      tools:\n        - name: list-clusters\n          description: \"List all ECS clusters in the account.\"\n          hints:\n            readOnly: true\n          call: \"ecs.list-clusters\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-clusters\n          description: \"Describe one or more ECS clusters.\"\n          hints:\n            readOnly: true\n          call: \"ecs.describe-clusters\"\n          with:\n            clusters: \"tools.clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-cluster\n          description: \"Create a new ECS cluster.\"\n          hints:\n            readOnly: false\n          call: \"ecs.create-cluster\"\n          with:\n            clusterName: \"tools.clusterName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-cluster\n          description: \"Delete an ECS cluster.\"\n          hints:\n            destructive: true\n          call: \"ecs.delete-cluster\"\n          with:\n            cluster: \"tools.cluster\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-services\n          description: \"List services in an ECS cluster.\"\n          hints:\n            readOnly: true\n          call: \"ecs.list-services\"\n          with:\n            cluster: \"tools.cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-services\n          description: \"Describe one or more ECS services.\"\n          hints:\n            readOnly: true\n          call: \"ecs.describe-services\"\n          with:\n            cluster: \"tools.cluster\"\n            services: \"tools.services\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-service\n          description: \"Create a new ECS service.\"\n          hints:\n            readOnly: false\n          call: \"ecs.create-service\"\n          with:\n            cluster: \"tools.cluster\"\n            serviceName:\
  \ \"tools.serviceName\"\n            taskDefinition: \"tools.taskDefinition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-service\n          description: \"Update an ECS service configuration.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"ecs.update-service\"\n          with:\n            cluster: \"tools.cluster\"\n            service: \"tools.service\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-service\n          description: \"Delete an ECS service.\"\n          hints:\n            destructive: true\n          call: \"ecs.delete-service\"\n          with:\n            cluster: \"tools.cluster\"\n            service: \"tools.service\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-task-definitions\n          description: \"List task definition\
  \ families or revisions.\"\n          hints:\n            readOnly: true\n          call: \"ecs.list-task-definitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-task-definition\n          description: \"Describe a task definition.\"\n          hints:\n            readOnly: true\n          call: \"ecs.describe-task-definition\"\n          with:\n            taskDefinition: \"tools.taskDefinition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: register-task-definition\n          description: \"Register a new task definition.\"\n          hints:\n            readOnly: false\n          call: \"ecs.register-task-definition\"\n          with:\n            family: \"tools.family\"\n            containerDefinitions: \"tools.containerDefinitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deregister-task-definition\n\
  \          description: \"Deregister a task definition revision.\"\n          hints:\n            destructive: true\n          call: \"ecs.deregister-task-definition\"\n          with:\n            taskDefinition: \"tools.taskDefinition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-task\n          description: \"Run a new task from a task definition.\"\n          hints:\n            readOnly: false\n          call: \"ecs.run-task\"\n          with:\n            cluster: \"tools.cluster\"\n            taskDefinition: \"tools.taskDefinition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-task\n          description: \"Stop a running task.\"\n          hints:\n            destructive: true\n          call: \"ecs.stop-task\"\n          with:\n            cluster: \"tools.cluster\"\n            task: \"tools.task\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: list-tasks\n          description: \"List tasks in a cluster.\"\n          hints:\n            readOnly: true\n          call: \"ecs.list-tasks\"\n          with:\n            cluster: \"tools.cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-tasks\n          description: \"Describe one or more tasks.\"\n          hints:\n            readOnly: true\n          call: \"ecs.describe-tasks\"\n          with:\n            cluster: \"tools.cluster\"\n            tasks: \"tools.tasks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-command\n          description: \"Execute a command in a running container.\"\n          hints:\n            readOnly: false\n          call: \"ecs.execute-command\"\n          with:\n            cluster: \"tools.cluster\"\n            task: \"tools.task\"\n            command:\
  \ \"tools.command\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ecs/refs/heads/main/capabilities/container-orchestration.yaml
tags:
- Amazon
- Containers
- Orchestration
tools:
- description: List all ECS clusters in the account.
  hints:
    readOnly: true
  name: list-clusters
- description: Describe one or more ECS clusters.
  hints:
    readOnly: true
  name: describe-clusters
- description: Create a new ECS cluster.
  hints:
    readOnly: false
  name: create-cluster
- description: Delete an ECS cluster.
  hints:
    destructive: true
  name: delete-cluster
- description: List services in an ECS cluster.
  hints:
    readOnly: true
  name: list-services
- description: Describe one or more ECS services.
  hints:
    readOnly: true
  name: describe-services
- description: Create a new ECS service.
  hints:
    readOnly: false
  name: create-service
- description: Update an ECS service configuration.
  hints:
    idempotent: true
    readOnly: false
  name: update-service
- description: Delete an ECS service.
  hints:
    destructive: true
  name: delete-service
- description: List task definition families or revisions.
  hints:
    readOnly: true
  name: list-task-definitions
- description: Describe a task definition.
  hints:
    readOnly: true
  name: describe-task-definition
- description: Register a new task definition.
  hints:
    readOnly: false
  name: register-task-definition
- description: Deregister a task definition revision.
  hints:
    destructive: true
  name: deregister-task-definition
- description: Run a new task from a task definition.
  hints:
    readOnly: false
  name: run-task
- description: Stop a running task.
  hints:
    destructive: true
  name: stop-task
- description: List tasks in a cluster.
  hints:
    readOnly: true
  name: list-tasks
- description: Describe one or more tasks.
  hints:
    readOnly: true
  name: describe-tasks
- description: Execute a command in a running container.
  hints:
    readOnly: false
  name: execute-command
---
