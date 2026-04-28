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
- virtual service management
- list meshes
- list virtual routers
- deprecated
- service mesh lifecycle management
- list virtual gateways for ingress traffic management
- microservices
- list all app mesh service meshes in the aws account
- virtual router management
- configuring routing rules for service-to-service communication
- aws
- manages service mesh infrastructure and inter-service communication
- managing gateway routing for external traffic ingress
- list all service meshes
- networking
- list virtual nodes
- aws app mesh
- list virtual services
- create a new app mesh service mesh
- envoy
- create mesh
- list virtual nodes in a mesh
- virtual gateway management
- list virtual gateways
- manage app mesh service meshes, virtual nodes, services, routers, and gateways
- virtual node management
- list virtual routers and their routing rules
- list virtual services in a mesh
- Platform Engineer
- list virtual routers in a mesh
- service mesh
- list virtual nodes in a service mesh
- list virtual gateways in a mesh
- create a new service mesh
- creating and configuring service meshes and their components
- list virtual services in a service mesh
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
