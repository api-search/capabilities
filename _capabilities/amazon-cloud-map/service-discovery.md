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
- create a service
- create service
- devops practitioners automating service registration and health monitoring
- list services registered in cloud map
- list instances
- cloud map
- list namespaces
- discover instances
- discover healthy service instances by namespace and service name
- aws
- dns
- discover healthy instances
- create a new cloud map service within a namespace
- list all namespaces
- manage services
- list services
- register instance
- list all cloud map service discovery namespaces
- amazon web services
- register an instance with a cloud map service
- discover service instances
- devops
- Platform Engineer
- dynamic service registry and health-based routing
- manage service discovery namespaces
- list all instances registered with a specific cloud map service
- dynamic microservice registration and discovery
- DevOps Engineer
- engineers managing service registries and microservice infrastructure
- microservices
- service discovery
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
