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
- Cloud Architect
- manage ecs clusters
- create a new ecs cluster
- delete cluster
- DevOps Engineer
- compute
- eks
- get detailed cluster information
- get cluster details
- containers
- deploy a persistent fargate service with load balancing and auto-scaling
- get status and details of running tasks
- full lifecycle management of serverless container workloads
- serverless
- delete a fargate cluster
- create a new cluster
- manage task execution
- deregister a task definition revision
- describe tasks
- create cluster
- register a task definition specifying container images, cpu, memory, and networking
- ecs
- amazon fargate
- create a service
- run task
- describe services
- get details of a task definition
- aws
- managing container lifecycle from definition to deployment
- update service
- manage task definitions
- describe task definition
- list all registered task definitions
- create service
- microservices
- delete a cluster
- list services
- register a task definition
- manage specific cluster
- running workloads without managing infrastructure
- launch a fargate task with specified cpu, memory, and networking
- architects designing serverless container solutions
- run a task
- scale or update a fargate service task count or definition
- devops
- engineers deploying and operating containerized applications
- Platform Engineer
- stop a running fargate task
- list task definitions
- describe clusters
- list clusters
- remove a fargate service from a cluster
- engineers building container platforms and infrastructure
- deploying and scaling microservices architectures
- list tasks
- get deployment status and health of fargate services
- list all ecs clusters for fargate workloads
- list all services running in a fargate cluster
- list tasks in a cluster with status filtering
- delete service
- deregister task definition
- register task definition
- list all ecs clusters
- stop task
- manage services
slug: amazon-fargate-container-orchestration
source_filename: amazon-fargate-container-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Fargate Container Orchestration\n  description: Workflow capability for deploying and managing serverless container workloads on Amazon Fargate. Combines cluster management, task definitions, task execution, and service deployment \n    for platform engineers and DevOps teams.\n  tags:\n  - Amazon Fargate\n  - Containers\n  - Serverless\n  - ECS\n  - DevOps\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: fargate\n    location: ./shared/fargate.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fargate-orchestration-api\n    description: Unified REST API for Amazon Fargate container orchestration.\n    resources:\n    - path: /v1/clusters\n      name: clusters\n      description: Manage ECS clusters\n      operations:\n  \
  \    - method: GET\n        name: list-clusters\n        description: List all ECS clusters\n        call: fargate.list-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cluster\n        description: Create a new cluster\n        call: fargate.create-cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{cluster}\n      name: cluster\n      description: Manage specific cluster\n      operations:\n      - method: GET\n        name: describe-clusters\n        description: Get cluster details\n        call: fargate.describe-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-cluster\n        description: Delete a cluster\n        call: fargate.delete-cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/task-definitions\n      name: task-definitions\n\
  \      description: Manage task definitions\n      operations:\n      - method: GET\n        name: list-task-definitions\n        description: List task definitions\n        call: fargate.list-task-definitions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: register-task-definition\n        description: Register a task definition\n        call: fargate.register-task-definition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: Manage task execution\n      operations:\n      - method: GET\n        name: list-tasks\n        description: List tasks\n        call: fargate.list-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: run-task\n        description: Run a task\n        call: fargate.run-task\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/services\n      name: services\n      description: Manage services\n      operations:\n      - method: GET\n        name: list-services\n        description: List services\n        call: fargate.list-services\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-service\n        description: Create a service\n        call: fargate.create-service\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fargate-orchestration-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Fargate container orchestration.\n    tools:\n    - name: list-clusters\n      description: List all ECS clusters for Fargate workloads\n      hints:\n        readOnly: true\n        openWorld: true\n      call: fargate.list-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cluster\n      description: Create\
  \ a new ECS cluster\n      hints:\n        readOnly: false\n      call: fargate.create-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-clusters\n      description: Get detailed cluster information\n      hints:\n        readOnly: true\n      call: fargate.describe-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cluster\n      description: Delete a Fargate cluster\n      hints:\n        readOnly: false\n        destructive: true\n      call: fargate.delete-cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-task-definition\n      description: Register a task definition specifying container images, CPU, memory, and networking\n      hints:\n        readOnly: false\n      call: fargate.register-task-definition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-task-definition\n      description: Get details\
  \ of a task definition\n      hints:\n        readOnly: true\n      call: fargate.describe-task-definition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-task-definitions\n      description: List all registered task definitions\n      hints:\n        readOnly: true\n      call: fargate.list-task-definitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deregister-task-definition\n      description: Deregister a task definition revision\n      hints:\n        readOnly: false\n        destructive: true\n      call: fargate.deregister-task-definition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-task\n      description: Launch a Fargate task with specified CPU, memory, and networking\n      hints:\n        readOnly: false\n      call: fargate.run-task\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-task\n      description: Stop a running Fargate\
  \ task\n      hints:\n        readOnly: false\n        destructive: true\n      call: fargate.stop-task\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-tasks\n      description: Get status and details of running tasks\n      hints:\n        readOnly: true\n      call: fargate.describe-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tasks\n      description: List tasks in a cluster with status filtering\n      hints:\n        readOnly: true\n      call: fargate.list-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-service\n      description: Deploy a persistent Fargate service with load balancing and auto-scaling\n      hints:\n        readOnly: false\n      call: fargate.create-service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-services\n      description: Get deployment status and health of Fargate services\n\
  \      hints:\n        readOnly: true\n      call: fargate.describe-services\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-services\n      description: List all services running in a Fargate cluster\n      hints:\n        readOnly: true\n      call: fargate.list-services\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-service\n      description: Scale or update a Fargate service task count or definition\n      hints:\n        readOnly: false\n      call: fargate.update-service\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-service\n      description: Remove a Fargate service from a cluster\n      hints:\n        readOnly: false\n        destructive: true\n      call: fargate.delete-service\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-fargate/refs/heads/main/capabilities/amazon-fargate-container-orchestration.yaml
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
