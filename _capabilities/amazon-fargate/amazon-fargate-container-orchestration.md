---
consumed_apis:
- fargate
description: Workflow capability for deploying and managing serverless container workloads on Amazon Fargate. Combines cluster management, task definitions, task execution, and service deployment for platform engineers and DevOps teams.
layout: capability
name: Amazon Fargate Container Orchestration
operations:
- description: List all ECS clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Create a new cluster
  method: POST
  name: create-cluster
  path: /v1/clusters
- description: Get cluster details
  method: GET
  name: describe-clusters
  path: /v1/clusters/{cluster}
- description: Delete a cluster
  method: DELETE
  name: delete-cluster
  path: /v1/clusters/{cluster}
- description: List task definitions
  method: GET
  name: list-task-definitions
  path: /v1/task-definitions
- description: Register a task definition
  method: POST
  name: register-task-definition
  path: /v1/task-definitions
- description: List tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
- description: Run a task
  method: POST
  name: run-task
  path: /v1/tasks
- description: List services
  method: GET
  name: list-services
  path: /v1/services
- description: Create a service
  method: POST
  name: create-service
  path: /v1/services
personas: []
provider_name: Amazon Fargate
provider_slug: amazon-fargate
search_terms:
- get detailed cluster information
- register a task definition
- get deployment status and health of fargate services
- Platform Engineer
- get status and details of running tasks
- compute
- register task definition
- list tasks
- DevOps Engineer
- create service
- engineers deploying and operating containerized applications
- manage specific cluster
- serverless
- list clusters
- run a task
- list task definitions
- list all ecs clusters
- describe task definition
- running workloads without managing infrastructure
- create a service
- deploying and scaling microservices architectures
- launch a fargate task with specified cpu, memory, and networking
- managing container lifecycle from definition to deployment
- describe clusters
- update service
- run task
- Cloud Architect
- devops
- stop task
- list all services running in a fargate cluster
- list all ecs clusters for fargate workloads
- describe tasks
- aws
- delete a cluster
- microservices
- stop a running fargate task
- register a task definition specifying container images, cpu, memory, and networking
- amazon fargate
- deregister task definition
- engineers building container platforms and infrastructure
- full lifecycle management of serverless container workloads
- ecs
- containers
- create a new cluster
- manage task execution
- deregister a task definition revision
- remove a fargate service from a cluster
- eks
- delete service
- manage services
- architects designing serverless container solutions
- list services
- get details of a task definition
- create cluster
- create a new ecs cluster
- manage ecs clusters
- delete a fargate cluster
- delete cluster
- list all registered task definitions
- list tasks in a cluster with status filtering
- manage task definitions
- describe services
- scale or update a fargate service task count or definition
- deploy a persistent fargate service with load balancing and auto-scaling
- get cluster details
slug: amazon-fargate-container-orchestration
tags:
- Amazon Fargate
- Containers
- Serverless
- ECS
- DevOps
tools:
- description: List all ECS clusters for Fargate workloads
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: Create a new ECS cluster
  hints:
    readOnly: false
  name: create-cluster
- description: Get detailed cluster information
  hints:
    readOnly: true
  name: describe-clusters
- description: Delete a Fargate cluster
  hints:
    destructive: true
    readOnly: false
  name: delete-cluster
- description: Register a task definition specifying container images, CPU, memory, and networking
  hints:
    readOnly: false
  name: register-task-definition
- description: Get details of a task definition
  hints:
    readOnly: true
  name: describe-task-definition
- description: List all registered task definitions
  hints:
    readOnly: true
  name: list-task-definitions
- description: Deregister a task definition revision
  hints:
    destructive: true
    readOnly: false
  name: deregister-task-definition
- description: Launch a Fargate task with specified CPU, memory, and networking
  hints:
    readOnly: false
  name: run-task
- description: Stop a running Fargate task
  hints:
    destructive: true
    readOnly: false
  name: stop-task
- description: Get status and details of running tasks
  hints:
    readOnly: true
  name: describe-tasks
- description: List tasks in a cluster with status filtering
  hints:
    readOnly: true
  name: list-tasks
- description: Deploy a persistent Fargate service with load balancing and auto-scaling
  hints:
    readOnly: false
  name: create-service
- description: Get deployment status and health of Fargate services
  hints:
    readOnly: true
  name: describe-services
- description: List all services running in a Fargate cluster
  hints:
    readOnly: true
  name: list-services
- description: Scale or update a Fargate service task count or definition
  hints:
    readOnly: false
  name: update-service
- description: Remove a Fargate service from a cluster
  hints:
    destructive: true
    readOnly: false
  name: delete-service
---
