---
categories: []
consumed_apis: []
description: The Amazon ECS API provides programmatic access to manage Fargate tasks and services through Amazon Elastic Container Service. AWS Fargate is a serverless compute engine for containers that removes the need to provision and manage servers. This specification covers the core ECS API operations relevant to Fargate workloads, including registering task definitions with Fargate compatibility, running tasks on Fargate infrastructure, and managing services with the Fargate launch type. All operations use the JSON-RPC style with POST requests and an X-Amz-Target header specifying the action.
layout: capability
name: AWS Fargate Amazon ECS API (Fargate)
operations:
- description: AWS Fargate Register a Fargate task definition
  method: POST
  name: registertaskdefinition
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.RegisterTaskDefinition
- description: AWS Fargate Describe a task definition
  method: POST
  name: describetaskdefinition
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeTaskDefinition
- description: AWS Fargate List task definitions
  method: POST
  name: listtaskdefinitions
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ListTaskDefinitions
- description: AWS Fargate Deregister a task definition
  method: POST
  name: deregistertaskdefinition
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DeregisterTaskDefinition
- description: AWS Fargate Run a Fargate task
  method: POST
  name: runtask
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.RunTask
- description: AWS Fargate Stop a running task
  method: POST
  name: stoptask
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.StopTask
- description: AWS Fargate Describe one or more tasks
  method: POST
  name: describetasks
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeTasks
- description: AWS Fargate List tasks in a cluster
  method: POST
  name: listtasks
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ListTasks
- description: AWS Fargate Create a Fargate service
  method: POST
  name: createservice
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.CreateService
- description: AWS Fargate Update a Fargate service
  method: POST
  name: updateservice
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.UpdateService
- description: AWS Fargate Delete a service
  method: POST
  name: deleteservice
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DeleteService
- description: AWS Fargate Describe one or more services
  method: POST
  name: describeservices
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeServices
- description: AWS Fargate List services in a cluster
  method: POST
  name: listservices
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ListServices
- description: AWS Fargate Create an ECS cluster
  method: POST
  name: createcluster
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.CreateCluster
- description: AWS Fargate Describe one or more clusters
  method: POST
  name: describeclusters
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeClusters
- description: AWS Fargate Execute a command in a Fargate task container
  method: POST
  name: executecommand
  path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ExecuteCommand
personas: []
provider_name: AWS Fargate
provider_slug: fargate
search_terms:
- listtasks
- aws fargate delete a service
- executecommand
- containers
- fargate
- aws fargate stop a running task
- aws fargate create an ecs cluster
- api
- createcluster
- aws fargate register a fargate task definition
- aws fargate describe one or more tasks
- updateservice
- deregistertaskdefinition
- aws fargate run a fargate task
- describeservices
- aws fargate execute a command in a fargate task container
- serverless
- kubernetes
- aws fargate deregister a task definition
- aws fargate update a fargate service
- compute
- describetasks
- runtask
- describeclusters
- aws fargate create a fargate service
- listtaskdefinitions
- aws fargate list tasks in a cluster
- describetaskdefinition
- aws fargate list services in a cluster
- registertaskdefinition
- aws fargate list task definitions
- aws fargate describe one or more services
- aws fargate describe one or more clusters
- docker
- deleteservice
- createservice
- stoptask
- aws fargate describe a task definition
- listservices
slug: fargate-capability
source_filename: fargate-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS Fargate Amazon ECS API (Fargate)\n  description: The Amazon ECS API provides programmatic access to manage Fargate tasks and services through Amazon Elastic\n    Container Service. AWS Fargate is a serverless compute engine for containers that removes the need to provision and manage\n    servers. This specification covers the core ECS API operations relevant to Fargate workloads, including registering task\n    definitions with Fargate compatibility, running tasks on Fargate infrastructure, and managing services with the Fargate\n    launch type. All operations use the JSON-RPC style with POST requests and an X-Amz-Target header specifying the action.\n  tags:\n  - Fargate\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fargate\n    baseUri: https://ecs.us-east-1.amazonaws.com\n    description: AWS Fargate Amazon ECS API (Fargate) HTTP API.\n    authentication:\n\
  \      type: apikey\n      in: header\n      name: Authorization\n      value: '{{FARGATE_TOKEN}}'\n    resources:\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.RegisterTaskDefinition\n      operations:\n      - name: registertaskdefinition\n        method: POST\n        description: AWS Fargate Register a Fargate task definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeTaskDefinition\n      operations:\n      - name: describetaskdefinition\n        method: POST\n        description: AWS Fargate Describe a task definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n\
  \      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ListTaskDefinitions\n      operations:\n      - name: listtaskdefinitions\n        method: POST\n        description: AWS Fargate List task definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DeregisterTaskDefinition\n      operations:\n      - name: deregistertaskdefinition\n        method: POST\n        description: AWS Fargate Deregister a task definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.RunTask\n      operations:\n      - name: runtask\n        method: POST\n        description: AWS Fargate Run a\
  \ Fargate task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.StopTask\n      operations:\n      - name: stoptask\n        method: POST\n        description: AWS Fargate Stop a running task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeTasks\n      operations:\n      - name: describetasks\n        method: POST\n        description: AWS Fargate Describe one or more tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ListTasks\n\
  \      operations:\n      - name: listtasks\n        method: POST\n        description: AWS Fargate List tasks in a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.CreateService\n      operations:\n      - name: createservice\n        method: POST\n        description: AWS Fargate Create a Fargate service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.UpdateService\n      operations:\n      - name: updateservice\n        method: POST\n        description: AWS Fargate Update a Fargate service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DeleteService\n      operations:\n      - name: deleteservice\n        method: POST\n        description: AWS Fargate Delete a service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeServices\n      operations:\n      - name: describeservices\n        method: POST\n        description: AWS Fargate Describe one or more services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ListServices\n      operations:\n     \
  \ - name: listservices\n        method: POST\n        description: AWS Fargate List services in a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.CreateCluster\n      operations:\n      - name: createcluster\n        method: POST\n        description: AWS Fargate Create an ECS cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeClusters\n      operations:\n      - name: describeclusters\n        method: POST\n        description: AWS Fargate Describe one or more clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: x-amz-target-amazonec2containerservicev20141113-\n      path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ExecuteCommand\n      operations:\n      - name: executecommand\n        method: POST\n        description: AWS Fargate Execute a command in a Fargate task container\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fargate-rest\n    description: REST adapter for AWS Fargate Amazon ECS API (Fargate).\n    resources:\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.RegisterTaskDefinition\n      name: registertaskdefinition\n      operations:\n      - method: POST\n        name: registertaskdefinition\n        description: AWS Fargate Register a Fargate task definition\n        call: fargate.registertaskdefinition\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeTaskDefinition\n      name: describetaskdefinition\n      operations:\n      - method: POST\n        name: describetaskdefinition\n        description: AWS Fargate Describe a task definition\n        call: fargate.describetaskdefinition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ListTaskDefinitions\n      name: listtaskdefinitions\n      operations:\n      - method: POST\n        name: listtaskdefinitions\n        description: AWS Fargate List task definitions\n        call: fargate.listtaskdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DeregisterTaskDefinition\n      name: deregistertaskdefinition\n      operations:\n      - method: POST\n        name: deregistertaskdefinition\n        description: AWS Fargate Deregister a\
  \ task definition\n        call: fargate.deregistertaskdefinition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.RunTask\n      name: runtask\n      operations:\n      - method: POST\n        name: runtask\n        description: AWS Fargate Run a Fargate task\n        call: fargate.runtask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.StopTask\n      name: stoptask\n      operations:\n      - method: POST\n        name: stoptask\n        description: AWS Fargate Stop a running task\n        call: fargate.stoptask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeTasks\n      name: describetasks\n      operations:\n      - method: POST\n        name: describetasks\n        description: AWS Fargate Describe one or more\
  \ tasks\n        call: fargate.describetasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ListTasks\n      name: listtasks\n      operations:\n      - method: POST\n        name: listtasks\n        description: AWS Fargate List tasks in a cluster\n        call: fargate.listtasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.CreateService\n      name: createservice\n      operations:\n      - method: POST\n        name: createservice\n        description: AWS Fargate Create a Fargate service\n        call: fargate.createservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.UpdateService\n      name: updateservice\n      operations:\n      - method: POST\n        name: updateservice\n        description: AWS Fargate Update\
  \ a Fargate service\n        call: fargate.updateservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DeleteService\n      name: deleteservice\n      operations:\n      - method: POST\n        name: deleteservice\n        description: AWS Fargate Delete a service\n        call: fargate.deleteservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeServices\n      name: describeservices\n      operations:\n      - method: POST\n        name: describeservices\n        description: AWS Fargate Describe one or more services\n        call: fargate.describeservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ListServices\n      name: listservices\n      operations:\n      - method: POST\n        name: listservices\n\
  \        description: AWS Fargate List services in a cluster\n        call: fargate.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.CreateCluster\n      name: createcluster\n      operations:\n      - method: POST\n        name: createcluster\n        description: AWS Fargate Create an ECS cluster\n        call: fargate.createcluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.DescribeClusters\n      name: describeclusters\n      operations:\n      - method: POST\n        name: describeclusters\n        description: AWS Fargate Describe one or more clusters\n        call: fargate.describeclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=AmazonEC2ContainerServiceV20141113.ExecuteCommand\n      name: executecommand\n      operations:\n\
  \      - method: POST\n        name: executecommand\n        description: AWS Fargate Execute a command in a Fargate task container\n        call: fargate.executecommand\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fargate-mcp\n    transport: http\n    description: MCP adapter for AWS Fargate Amazon ECS API (Fargate) for AI agent use.\n    tools:\n    - name: registertaskdefinition\n      description: AWS Fargate Register a Fargate task definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.registertaskdefinition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describetaskdefinition\n      description: AWS Fargate Describe a task definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.describetaskdefinition\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: listtaskdefinitions\n      description: AWS Fargate List task definitions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.listtaskdefinitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deregistertaskdefinition\n      description: AWS Fargate Deregister a task definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.deregistertaskdefinition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runtask\n      description: AWS Fargate Run a Fargate task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.runtask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stoptask\n      description: AWS Fargate Stop a running task\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: fargate.stoptask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describetasks\n      description: AWS Fargate Describe one or more tasks\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.describetasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtasks\n      description: AWS Fargate List tasks in a cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.listtasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createservice\n      description: AWS Fargate Create a Fargate service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.createservice\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: updateservice\n      description: AWS Fargate Update a Fargate service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.updateservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteservice\n      description: AWS Fargate Delete a service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.deleteservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeservices\n      description: AWS Fargate Describe one or more services\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.describeservices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservices\n      description: AWS Fargate List services in a cluster\n      hints:\n        readOnly: false\n        destructive: false\n \
  \       idempotent: false\n      call: fargate.listservices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcluster\n      description: AWS Fargate Create an ECS cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.createcluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describeclusters\n      description: AWS Fargate Describe one or more clusters\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.describeclusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executecommand\n      description: AWS Fargate Execute a command in a Fargate task container\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fargate.executecommand\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  binds:\n- namespace: env\n  keys:\n    FARGATE_TOKEN: FARGATE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fargate/refs/heads/main/capabilities/fargate-capability.yaml
tags:
- Fargate
- API
tools:
- description: AWS Fargate Register a Fargate task definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registertaskdefinition
- description: AWS Fargate Describe a task definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describetaskdefinition
- description: AWS Fargate List task definitions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listtaskdefinitions
- description: AWS Fargate Deregister a task definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deregistertaskdefinition
- description: AWS Fargate Run a Fargate task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runtask
- description: AWS Fargate Stop a running task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stoptask
- description: AWS Fargate Describe one or more tasks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describetasks
- description: AWS Fargate List tasks in a cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listtasks
- description: AWS Fargate Create a Fargate service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservice
- description: AWS Fargate Update a Fargate service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateservice
- description: AWS Fargate Delete a service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleteservice
- description: AWS Fargate Describe one or more services
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describeservices
- description: AWS Fargate List services in a cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listservices
- description: AWS Fargate Create an ECS cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcluster
- description: AWS Fargate Describe one or more clusters
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describeclusters
- description: AWS Fargate Execute a command in a Fargate task container
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executecommand
---
