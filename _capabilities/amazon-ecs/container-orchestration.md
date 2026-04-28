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
- delete cluster
- list tasks
- stop a running task.
- list task definitions
- ecs task execution.
- list task definition families or revisions.
- update an ecs service configuration.
- list services
- create a new service.
- ecs service management.
- run a new task from a task definition.
- register task definition
- register a new task definition.
- docker
- describe clusters
- create cluster
- deregister a task definition revision.
- orchestration
- create a new ecs service.
- delete an ecs service.
- run task
- list clusters
- ecs
- list all ecs clusters.
- create a new ecs cluster.
- list tasks in a cluster.
- run a new task.
- list services in an ecs cluster.
- describe services
- execute command
- deregister task definition
- stop task
- update service
- containers
- describe tasks
- create service
- describe one or more ecs services.
- describe a task definition.
- ecs cluster management.
- list services in a cluster.
- describe one or more tasks.
- delete service
- list task definitions.
- describe one or more ecs clusters.
- aws
- describe task definition
- execute a command in a running container.
- ecs task definition management.
- delete an ecs cluster.
- list all ecs clusters in the account.
- amazon
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
