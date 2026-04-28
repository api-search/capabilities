---
categories:
- container-orchestration
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
- list all services running in a fargate cluster
- delete cluster
- list tasks
- list task definitions
- list all registered task definitions
- running workloads without managing infrastructure
- create a new cluster
- eks
- delete a fargate cluster
- list services
- full lifecycle management of serverless container workloads
- serverless
- manage task execution
- list all ecs clusters for fargate workloads
- register task definition
- stop a running fargate task
- describe clusters
- create cluster
- list all ecs clusters
- deregister a task definition revision
- get status and details of running tasks
- deploy a persistent fargate service with load balancing and auto-scaling
- run task
- list clusters
- ecs
- manage specific cluster
- DevOps Engineer
- engineers deploying and operating containerized applications
- architects designing serverless container solutions
- describe services
- engineers building container platforms and infrastructure
- run a task
- amazon fargate
- delete a cluster
- manage task definitions
- deregister task definition
- stop task
- scale or update a fargate service task count or definition
- update service
- get deployment status and health of fargate services
- containers
- describe tasks
- create service
- devops
- get detailed cluster information
- manage ecs clusters
- get details of a task definition
- managing container lifecycle from definition to deployment
- list tasks in a cluster with status filtering
- deploying and scaling microservices architectures
- create a new ecs cluster
- launch a fargate task with specified cpu, memory, and networking
- delete service
- get cluster details
- aws
- register a task definition specifying container images, cpu, memory, and networking
- create a service
- register a task definition
- describe task definition
- Cloud Architect
- manage services
- microservices
- remove a fargate service from a cluster
- compute
- Platform Engineer
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
