---
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
- list all cloud map service discovery namespaces
- create a new cloud map service within a namespace
- list namespaces
- engineers managing service registries and microservice infrastructure
- devops practitioners automating service registration and health monitoring
- discover healthy instances
- discover healthy service instances by namespace and service name
- manage service discovery namespaces
- list instances
- amazon web services
- dns
- dynamic microservice registration and discovery
- Platform Engineer
- service discovery
- microservices
- list services
- register instance
- devops
- discover service instances
- dynamic service registry and health-based routing
- cloud map
- create service
- discover instances
- list all namespaces
- DevOps Engineer
- list services registered in cloud map
- aws
- list all instances registered with a specific cloud map service
- manage services
- create a service
- register an instance with a cloud map service
slug: service-discovery
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
