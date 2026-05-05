---
categories: []
consumed_apis:
- app-mesh
description: 'Workflow capability for platform engineers to manage App Mesh service meshes, virtual nodes, virtual services, and traffic routing. Note: AWS App Mesh is deprecated; Amazon ECS Service Connect is the recommended replacement for new deployments.'
layout: capability
name: AWS App Mesh Service Mesh Workflow
operations:
- description: List all service meshes
  method: GET
  name: list-meshes
  path: /v1/meshes
- description: Create a new service mesh
  method: POST
  name: create-mesh
  path: /v1/meshes
- description: List virtual nodes in a mesh
  method: GET
  name: list-virtual-nodes
  path: /v1/meshes/{meshName}/virtual-nodes
- description: List virtual services in a mesh
  method: GET
  name: list-virtual-services
  path: /v1/meshes/{meshName}/virtual-services
- description: List virtual routers in a mesh
  method: GET
  name: list-virtual-routers
  path: /v1/meshes/{meshName}/virtual-routers
- description: List virtual gateways in a mesh
  method: GET
  name: list-virtual-gateways
  path: /v1/meshes/{meshName}/virtual-gateways
personas: []
provider_name: AWS App Mesh
provider_slug: aws-app-mesh
search_terms:
- aws
- list virtual gateways in a mesh
- deprecated
- list virtual nodes in a service mesh
- configuring routing rules for service-to-service communication
- list virtual nodes
- list virtual routers
- Platform Engineer
- virtual gateway management
- creating and configuring service meshes and their components
- list virtual routers in a mesh
- create a new app mesh service mesh
- service mesh
- list meshes
- virtual router management
- aws app mesh
- list virtual routers and their routing rules
- manages service mesh infrastructure and inter-service communication
- microservices
- virtual service management
- envoy
- manage app mesh service meshes, virtual nodes, services, routers, and gateways
- networking
- list virtual gateways for ingress traffic management
- list all app mesh service meshes in the aws account
- list virtual services in a service mesh
- virtual node management
- create mesh
- list virtual nodes in a mesh
- list virtual gateways
- list all service meshes
- service mesh lifecycle management
- list virtual services
- list virtual services in a mesh
- managing gateway routing for external traffic ingress
- create a new service mesh
slug: service-mesh-workflow
source_filename: service-mesh-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AWS App Mesh Service Mesh Workflow\"\n  description: \"Workflow capability for platform engineers to manage App Mesh service meshes, virtual nodes, virtual services, and traffic routing. Note: AWS App Mesh is deprecated; Amazon ECS Service Connect is the recommended replacement for new deployments.\"\n  tags:\n    - AWS App Mesh\n    - AWS\n    - Service Mesh\n    - Microservices\n    - Networking\n    - Deprecated\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: app-mesh\n      location: ./shared/app-mesh.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: app-mesh-workflow-api\n      description: \"Unified REST API for AWS App Mesh service mesh management.\"\n      resources:\n        - path:\
  \ /v1/meshes\n          name: meshes\n          description: \"Service mesh lifecycle management\"\n          operations:\n            - method: GET\n              name: list-meshes\n              description: \"List all service meshes\"\n              call: \"app-mesh.list-meshes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-mesh\n              description: \"Create a new service mesh\"\n              call: \"app-mesh.create-mesh\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meshes/{meshName}/virtual-nodes\n          name: virtual-nodes\n          description: \"Virtual node management\"\n          operations:\n            - method: GET\n              name: list-virtual-nodes\n              description: \"List virtual nodes in a mesh\"\n              call: \"app-mesh.list-virtual-nodes\"\n         \
  \     with:\n                meshName: \"rest.meshName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meshes/{meshName}/virtual-services\n          name: virtual-services\n          description: \"Virtual service management\"\n          operations:\n            - method: GET\n              name: list-virtual-services\n              description: \"List virtual services in a mesh\"\n              call: \"app-mesh.list-virtual-services\"\n              with:\n                meshName: \"rest.meshName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meshes/{meshName}/virtual-routers\n          name: virtual-routers\n          description: \"Virtual router management\"\n          operations:\n            - method: GET\n              name: list-virtual-routers\n              description: \"List virtual routers in a mesh\"\n              call: \"\
  app-mesh.list-virtual-routers\"\n              with:\n                meshName: \"rest.meshName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meshes/{meshName}/virtual-gateways\n          name: virtual-gateways\n          description: \"Virtual gateway management\"\n          operations:\n            - method: GET\n              name: list-virtual-gateways\n              description: \"List virtual gateways in a mesh\"\n              call: \"app-mesh.list-virtual-gateways\"\n              with:\n                meshName: \"rest.meshName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: app-mesh-workflow-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AWS App Mesh service mesh management.\"\n      tools:\n        - name: list-meshes\n          description: \"List all App Mesh service\
  \ meshes in the AWS account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"app-mesh.list-meshes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-mesh\n          description: \"Create a new App Mesh service mesh\"\n          hints:\n            readOnly: false\n          call: \"app-mesh.create-mesh\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-virtual-nodes\n          description: \"List virtual nodes in a service mesh\"\n          hints:\n            readOnly: true\n          call: \"app-mesh.list-virtual-nodes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-virtual-services\n          description: \"List virtual services in a service mesh\"\n          hints:\n            readOnly: true\n          call: \"app-mesh.list-virtual-services\"\n     \
  \     outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-virtual-routers\n          description: \"List virtual routers and their routing rules\"\n          hints:\n            readOnly: true\n          call: \"app-mesh.list-virtual-routers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-virtual-gateways\n          description: \"List virtual gateways for ingress traffic management\"\n          hints:\n            readOnly: true\n          call: \"app-mesh.list-virtual-gateways\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-app-mesh/refs/heads/main/capabilities/service-mesh-workflow.yaml
tags:
- AWS App Mesh
- Service Mesh
- Microservices
- Networking
- Deprecated
tools:
- description: List all App Mesh service meshes in the AWS account
  hints:
    openWorld: true
    readOnly: true
  name: list-meshes
- description: Create a new App Mesh service mesh
  hints:
    readOnly: false
  name: create-mesh
- description: List virtual nodes in a service mesh
  hints:
    readOnly: true
  name: list-virtual-nodes
- description: List virtual services in a service mesh
  hints:
    readOnly: true
  name: list-virtual-services
- description: List virtual routers and their routing rules
  hints:
    readOnly: true
  name: list-virtual-routers
- description: List virtual gateways for ingress traffic management
  hints:
    readOnly: true
  name: list-virtual-gateways
---
