---
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
- run task
- ecs service management.
- delete cluster
- list clusters
- create a new service.
- list tasks in a cluster.
- describe one or more ecs clusters.
- containers
- list task definitions
- update an ecs service configuration.
- register task definition
- docker
- run a new task.
- create a new ecs service.
- list services
- list services in an ecs cluster.
- register a new task definition.
- delete service
- list tasks
- stop task
- list task definitions.
- stop a running task.
- list all ecs clusters.
- list all ecs clusters in the account.
- ecs task execution.
- orchestration
- describe task definition
- delete an ecs cluster.
- describe one or more ecs services.
- update service
- execute command
- execute a command in a running container.
- create a new ecs cluster.
- describe clusters
- amazon
- describe a task definition.
- ecs cluster management.
- deregister a task definition revision.
- ecs
- delete an ecs service.
- create cluster
- describe services
- run a new task from a task definition.
- describe one or more tasks.
- aws
- list task definition families or revisions.
- describe tasks
- ecs task definition management.
- list services in a cluster.
- create service
- deregister task definition
slug: container-orchestration
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
