---
consumed_apis:
- rest-api
description: Unified platform management capability for OpenShift clusters including projects, builds, deployments, routes, and monitoring. Used by platform engineers and cluster administrators.
layout: capability
name: OpenShift Platform Management
operations:
- description: List projects
  method: GET
  name: list-projects
  path: /v1/projects
personas: []
provider_name: OpenShift
provider_slug: openshift
search_terms:
- list image streams
- get pod details
- list cluster nodes
- paas
- devops
- list pods
- list installed operators
- openshift
- get project details
- list deployments
- get pod
- list builds
- list persistent volumes
- project management
- list operators
- list configmaps
- containers
- list nodes
- list projects
- list images
- platform
- list services
- list config maps
- list storage
- list openshift projects
- get project
- list routes
- ci/cd
- kubernetes
- enterprise
- cloud native
slug: platform-management
tags:
- OpenShift
- Kubernetes
- Platform
- DevOps
tools:
- description: List OpenShift projects
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Get project details
  hints:
    readOnly: true
  name: get-project
- description: List builds
  hints:
    readOnly: true
  name: list-builds
- description: List routes
  hints:
    readOnly: true
  name: list-routes
- description: List deployments
  hints:
    readOnly: true
  name: list-deployments
- description: List pods
  hints:
    readOnly: true
  name: list-pods
- description: Get pod details
  hints:
    readOnly: true
  name: get-pod
- description: List services
  hints:
    readOnly: true
  name: list-services
- description: List config maps
  hints:
    readOnly: true
  name: list-configmaps
- description: List cluster nodes
  hints:
    readOnly: true
  name: list-nodes
- description: List installed operators
  hints:
    readOnly: true
  name: list-operators
- description: List image streams
  hints:
    readOnly: true
  name: list-images
- description: List persistent volumes
  hints:
    readOnly: true
  name: list-storage
---
