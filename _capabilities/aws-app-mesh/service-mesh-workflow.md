---
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
- aws app mesh
- networking
- virtual service management
- Platform Engineer
- list virtual routers in a mesh
- manages service mesh infrastructure and inter-service communication
- list virtual gateways
- list virtual services
- deprecated
- virtual gateway management
- list virtual services in a service mesh
- list virtual gateways for ingress traffic management
- list meshes
- list virtual nodes
- create mesh
- manage app mesh service meshes, virtual nodes, services, routers, and gateways
- list virtual routers
- list all service meshes
- creating and configuring service meshes and their components
- list virtual routers and their routing rules
- list virtual services in a mesh
- microservices
- envoy
- configuring routing rules for service-to-service communication
- service mesh lifecycle management
- create a new app mesh service mesh
- list virtual nodes in a service mesh
- list virtual gateways in a mesh
- managing gateway routing for external traffic ingress
- create a new service mesh
- virtual node management
- virtual router management
- service mesh
- list virtual nodes in a mesh
- list all app mesh service meshes in the aws account
slug: service-mesh-workflow
tags:
- AWS App Mesh
- AWS
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
