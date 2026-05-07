---
categories: []
consumed_apis: []
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
- managing gateway routing for external traffic ingress
- list virtual nodes in a service mesh
- networking
- list virtual nodes in a mesh
- list virtual routers and their routing rules
- virtual gateway management
- manage app mesh service meshes, virtual nodes, services, routers, and gateways
- list virtual nodes
- service mesh
- deprecated
- list meshes
- create a new service mesh
- list virtual gateways in a mesh
- list virtual routers
- Platform Engineer
- list all app mesh service meshes in the aws account
- list virtual services
- virtual node management
- configuring routing rules for service-to-service communication
- list virtual services in a mesh
- virtual router management
- list virtual routers in a mesh
- creating and configuring service meshes and their components
- list virtual gateways for ingress traffic management
- aws app mesh
- envoy
- list all service meshes
- manages service mesh infrastructure and inter-service communication
- create a new app mesh service mesh
- aws
- create mesh
- virtual service management
- microservices
- list virtual gateways
- list virtual services in a service mesh
- service mesh lifecycle management
slug: service-mesh-workflow
source_filename: service-mesh-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS App Mesh Service Mesh Workflow\n  description: 'Workflow capability for platform engineers to manage App Mesh service meshes, virtual nodes, virtual services,\n    and traffic routing. Note: AWS App Mesh is deprecated; Amazon ECS Service Connect is the recommended replacement for new\n    deployments.'\n  tags:\n  - AWS App Mesh\n  - AWS\n  - Service Mesh\n  - Microservices\n  - Networking\n  - Deprecated\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: app-mesh\n    baseUri: https://appmesh.{region}.amazonaws.com\n    description: AWS App Mesh control plane API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_SIGV4_TOKEN}}'\n      placement: header\n    resources:\n    - name: meshes\n\
  \      path: /v20190125/meshes\n      description: Manage service meshes\n      operations:\n      - name: list-meshes\n        method: GET\n        description: List all service meshes in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-mesh\n        method: PUT\n        description: Create a new service mesh\n        body:\n          type: json\n          data:\n            meshName: '{{tools.mesh_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: virtual-nodes\n      path: /v20190125/meshes/{meshName}/virtualNodes\n      description: Manage virtual nodes within a mesh\n      operations:\n      - name: list-virtual-nodes\n        method: GET\n        description: List virtual nodes in a mesh\n        inputParameters:\n        - name: meshName\n          in: path\n          type:\
  \ string\n          required: true\n          description: The name of the service mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: virtual-services\n      path: /v20190125/meshes/{meshName}/virtualServices\n      description: Manage virtual services\n      operations:\n      - name: list-virtual-services\n        method: GET\n        description: List virtual services in a mesh\n        inputParameters:\n        - name: meshName\n          in: path\n          type: string\n          required: true\n          description: The name of the service mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: virtual-routers\n      path: /v20190125/meshes/{meshName}/virtualRouters\n      description: Manage virtual routers\n      operations:\n      - name: list-virtual-routers\n        method: GET\n        description:\
  \ List virtual routers in a mesh\n        inputParameters:\n        - name: meshName\n          in: path\n          type: string\n          required: true\n          description: The name of the service mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: virtual-gateways\n      path: /v20190125/meshes/{meshName}/virtualGateways\n      description: Manage virtual gateways\n      operations:\n      - name: list-virtual-gateways\n        method: GET\n        description: List virtual gateways in a mesh\n        inputParameters:\n        - name: meshName\n          in: path\n          type: string\n          required: true\n          description: The name of the service mesh\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: app-mesh-workflow-api\n    description:\
  \ Unified REST API for AWS App Mesh service mesh management.\n    resources:\n    - path: /v1/meshes\n      name: meshes\n      description: Service mesh lifecycle management\n      operations:\n      - method: GET\n        name: list-meshes\n        description: List all service meshes\n        call: app-mesh.list-meshes\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-mesh\n        description: Create a new service mesh\n        call: app-mesh.create-mesh\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meshes/{meshName}/virtual-nodes\n      name: virtual-nodes\n      description: Virtual node management\n      operations:\n      - method: GET\n        name: list-virtual-nodes\n        description: List virtual nodes in a mesh\n        call: app-mesh.list-virtual-nodes\n        with:\n          meshName: rest.meshName\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /v1/meshes/{meshName}/virtual-services\n      name: virtual-services\n      description: Virtual service management\n      operations:\n      - method: GET\n        name: list-virtual-services\n        description: List virtual services in a mesh\n        call: app-mesh.list-virtual-services\n        with:\n          meshName: rest.meshName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meshes/{meshName}/virtual-routers\n      name: virtual-routers\n      description: Virtual router management\n      operations:\n      - method: GET\n        name: list-virtual-routers\n        description: List virtual routers in a mesh\n        call: app-mesh.list-virtual-routers\n        with:\n          meshName: rest.meshName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meshes/{meshName}/virtual-gateways\n      name: virtual-gateways\n      description: Virtual gateway management\n\
  \      operations:\n      - method: GET\n        name: list-virtual-gateways\n        description: List virtual gateways in a mesh\n        call: app-mesh.list-virtual-gateways\n        with:\n          meshName: rest.meshName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: app-mesh-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted AWS App Mesh service mesh management.\n    tools:\n    - name: list-meshes\n      description: List all App Mesh service meshes in the AWS account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: app-mesh.list-meshes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-mesh\n      description: Create a new App Mesh service mesh\n      hints:\n        readOnly: false\n      call: app-mesh.create-mesh\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-virtual-nodes\n\
  \      description: List virtual nodes in a service mesh\n      hints:\n        readOnly: true\n      call: app-mesh.list-virtual-nodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-virtual-services\n      description: List virtual services in a service mesh\n      hints:\n        readOnly: true\n      call: app-mesh.list-virtual-services\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-virtual-routers\n      description: List virtual routers and their routing rules\n      hints:\n        readOnly: true\n      call: app-mesh.list-virtual-routers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-virtual-gateways\n      description: List virtual gateways for ingress traffic management\n      hints:\n        readOnly: true\n      call: app-mesh.list-virtual-gateways\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
