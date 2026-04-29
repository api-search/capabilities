---
categories:
- container-orchestration
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
- list cluster nodes
- list operators
- cloud native
- openshift
- get pod
- containers
- kubernetes
- list pods
- project management
- list configmaps
- enterprise
- list storage
- get project details
- list persistent volumes
- list image streams
- get project
- ci/cd
- list installed operators
- paas
- list images
- list services
- list routes
- devops
- list config maps
- platform
- list nodes
- list builds
- list projects
- list openshift projects
- get pod details
- list deployments
slug: platform-management
source_filename: platform-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"OpenShift Platform Management\"\n  description: \"Unified platform management capability for OpenShift clusters including projects, builds, deployments, routes, and monitoring. Used by platform engineers and cluster administrators.\"\n  tags: [OpenShift, Kubernetes, Platform, DevOps]\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\nbinds:\n  - namespace: env\n    keys:\n      OPENSHIFT_TOKEN: OPENSHIFT_TOKEN\ncapability:\n  consumes:\n    - import: rest-api\n      location: ./shared/rest-api.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: platform-management-api\n      description: \"Unified REST API for OpenShift platform management.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description: \"Project management\"\n          operations:\n            - { method: GET, name: list-projects, description: \"List projects\", call: \"rest-api.list-projects\", outputParameters:\
  \ [{ type: object, mapping: \"$.\" }] }\n    - type: mcp\n      port: 9090\n      namespace: platform-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted OpenShift platform management.\"\n      tools:\n        - { name: list-projects, description: \"List OpenShift projects\", hints: { readOnly: true, openWorld: true }, call: \"rest-api.list-projects\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-project, description: \"Get project details\", hints: { readOnly: true }, call: \"rest-api.get-project\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-builds, description: \"List builds\", hints: { readOnly: true }, call: \"rest-api.list-builds\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-routes, description: \"List routes\", hints: { readOnly: true }, call: \"rest-api.list-routes\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name:\
  \ list-deployments, description: \"List deployments\", hints: { readOnly: true }, call: \"rest-api.list-deployments\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-pods, description: \"List pods\", hints: { readOnly: true }, call: \"rest-api.list-pods\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-pod, description: \"Get pod details\", hints: { readOnly: true }, call: \"rest-api.get-pod\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-services, description: \"List services\", hints: { readOnly: true }, call: \"rest-api.list-services\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-configmaps, description: \"List config maps\", hints: { readOnly: true }, call: \"rest-api.list-configmaps\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-nodes, description: \"List cluster nodes\", hints: { readOnly: true }, call: \"rest-api.list-nodes\"\
  , outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-operators, description: \"List installed operators\", hints: { readOnly: true }, call: \"rest-api.list-operators\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-images, description: \"List image streams\", hints: { readOnly: true }, call: \"rest-api.list-images\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-storage, description: \"List persistent volumes\", hints: { readOnly: true }, call: \"rest-api.list-storage\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openshift/refs/heads/main/capabilities/platform-management.yaml
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
