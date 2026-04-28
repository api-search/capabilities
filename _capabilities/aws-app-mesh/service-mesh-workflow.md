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
- list all service meshes
- service mesh lifecycle management
- configuring routing rules for service-to-service communication
- virtual service management
- virtual node management
- manage app mesh service meshes, virtual nodes, services, routers, and gateways
- list virtual nodes in a mesh
- list all app mesh service meshes in the aws account
- virtual gateway management
- list virtual routers in a mesh
- list virtual services in a service mesh
- virtual router management
- manages service mesh infrastructure and inter-service communication
- create a new app mesh service mesh
- create mesh
- list virtual nodes in a service mesh
- list virtual gateways for ingress traffic management
- aws app mesh
- list virtual routers
- service mesh
- networking
- create a new service mesh
- list virtual services in a mesh
- list virtual gateways in a mesh
- list virtual routers and their routing rules
- envoy
- managing gateway routing for external traffic ingress
- list virtual nodes
- list virtual gateways
- list meshes
- aws
- deprecated
- list virtual services
- microservices
- creating and configuring service meshes and their components
- Platform Engineer
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
