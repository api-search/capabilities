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
- get cluster details
- stop task
- deploy a persistent fargate service with load balancing and auto-scaling
- Platform Engineer
- delete service
- engineers building container platforms and infrastructure
- create a service
- stop a running fargate task
- describe services
- serverless
- aws
- list services
- engineers deploying and operating containerized applications
- eks
- DevOps Engineer
- list task definitions
- deregister task definition
- list clusters
- delete a cluster
- get details of a task definition
- run a task
- remove a fargate service from a cluster
- containers
- register a task definition
- list tasks
- manage specific cluster
- ecs
- running workloads without managing infrastructure
- list all registered task definitions
- Cloud Architect
- architects designing serverless container solutions
- create cluster
- manage task definitions
- list tasks in a cluster with status filtering
- manage ecs clusters
- get status and details of running tasks
- get deployment status and health of fargate services
- scale or update a fargate service task count or definition
- deploying and scaling microservices architectures
- delete a fargate cluster
- describe tasks
- microservices
- list all ecs clusters
- devops
- create a new ecs cluster
- managing container lifecycle from definition to deployment
- create a new cluster
- run task
- register a task definition specifying container images, cpu, memory, and networking
- describe task definition
- list all services running in a fargate cluster
- delete cluster
- amazon fargate
- manage task execution
- create service
- launch a fargate task with specified cpu, memory, and networking
- update service
- compute
- describe clusters
- full lifecycle management of serverless container workloads
- get detailed cluster information
- register task definition
- manage services
- deregister a task definition revision
- list all ecs clusters for fargate workloads
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
