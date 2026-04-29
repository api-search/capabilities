---
categories: []
consumed_apis:
- cloudmap
description: Workflow for dynamically discovering and registering microservices using AWS Cloud Map, enabling DevOps and platform engineers to maintain service registries with health-based routing.
layout: capability
name: Amazon Cloud Map Service Discovery
operations:
- description: List all namespaces
  method: GET
  name: list-namespaces
  path: /v1/namespaces
- description: List services
  method: GET
  name: list-services
  path: /v1/services
- description: Create a service
  method: POST
  name: create-service
  path: /v1/services
- description: Discover healthy instances
  method: POST
  name: discover-instances
  path: /v1/discover
personas: []
provider_name: Amazon Cloud Map
provider_slug: amazon-cloud-map
search_terms:
- aws
- list services registered in cloud map
- dynamic service registry and health-based routing
- service discovery
- list namespaces
- discover healthy instances
- DevOps Engineer
- engineers managing service registries and microservice infrastructure
- discover service instances
- create service
- dns
- create a service
- cloud map
- list instances
- Platform Engineer
- list all instances registered with a specific cloud map service
- manage services
- list all namespaces
- discover healthy service instances by namespace and service name
- register instance
- dynamic microservice registration and discovery
- devops practitioners automating service registration and health monitoring
- register an instance with a cloud map service
- amazon web services
- list services
- microservices
- manage service discovery namespaces
- devops
- create a new cloud map service within a namespace
- list all cloud map service discovery namespaces
- discover instances
slug: service-discovery
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Cloud Map Service Discovery\"\n  description: \"Workflow for dynamically discovering and registering microservices using AWS Cloud Map, enabling DevOps and platform engineers to maintain service registries with health-based routing.\"\n  tags:\n    - Amazon Web Services\n    - Cloud Map\n    - Service Discovery\n    - Microservices\n    - DevOps\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cloudmap\n      location: ./shared/cloud-map.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: service-discovery-api\n      description: \"Unified REST API for AWS Cloud Map service discovery operations.\"\n      resources:\n        - path: /v1/namespaces\n          name: namespaces\n          description:\
  \ \"Manage service discovery namespaces\"\n          operations:\n            - method: GET\n              name: list-namespaces\n              description: \"List all namespaces\"\n              call: \"cloudmap.list-namespaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/services\n          name: services\n          description: \"Manage services\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List services\"\n              call: \"cloudmap.list-services\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-service\n              description: \"Create a service\"\n              call: \"cloudmap.create-service\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/discover\n\
  \          name: discover\n          description: \"Discover service instances\"\n          operations:\n            - method: POST\n              name: discover-instances\n              description: \"Discover healthy instances\"\n              call: \"cloudmap.discover-instances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: service-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted service discovery using AWS Cloud Map.\"\n      tools:\n        - name: list-namespaces\n          description: \"List all Cloud Map service discovery namespaces\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudmap.list-namespaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-services\n          description: \"List services registered in Cloud Map\"\
  \n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudmap.list-services\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-service\n          description: \"Create a new Cloud Map service within a namespace\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"cloudmap.create-service\"\n          with:\n            Name: \"tools.name\"\n            NamespaceId: \"tools.namespace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: discover-instances\n          description: \"Discover healthy service instances by namespace and service name\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudmap.discover-instances\"\n          with:\n            NamespaceName: \"tools.namespace_name\"\n            ServiceName: \"tools.service_name\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: register-instance\n          description: \"Register an instance with a Cloud Map service\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"cloudmap.register-instance\"\n          with:\n            ServiceId: \"tools.service_id\"\n            InstanceId: \"tools.instance_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-instances\n          description: \"List all instances registered with a specific Cloud Map service\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cloudmap.list-instances\"\n          with:\n            ServiceId: \"tools.service_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cloud-map/refs/heads/main/capabilities/service-discovery.yaml
tags:
- Amazon Web Services
- Cloud Map
- Service Discovery
- Microservices
- DevOps
tools:
- description: List all Cloud Map service discovery namespaces
  hints:
    idempotent: true
    readOnly: true
  name: list-namespaces
- description: List services registered in Cloud Map
  hints:
    idempotent: true
    readOnly: true
  name: list-services
- description: Create a new Cloud Map service within a namespace
  hints:
    idempotent: false
    readOnly: false
  name: create-service
- description: Discover healthy service instances by namespace and service name
  hints:
    idempotent: true
    readOnly: true
  name: discover-instances
- description: Register an instance with a Cloud Map service
  hints:
    idempotent: false
    readOnly: false
  name: register-instance
- description: List all instances registered with a specific Cloud Map service
  hints:
    idempotent: true
    readOnly: true
  name: list-instances
---
