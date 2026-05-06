---
categories:
- container-orchestration
consumed_apis: []
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
- list builds
- list persistent volumes
- get project details
- list configmaps
- get pod details
- devops
- list operators
- list openshift projects
- list services
- list nodes
- list deployments
- containers
- list image streams
- enterprise
- cloud native
- list cluster nodes
- project management
- kubernetes
- ci/cd
- list routes
- get project
- list projects
- list storage
- list config maps
- list installed operators
- platform
- openshift
- get pod
- list pods
- list images
- paas
slug: platform-management
source_filename: platform-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenShift Platform Management\n  description: Unified platform management capability for OpenShift clusters including projects, builds, deployments, routes,\n    and monitoring. Used by platform engineers and cluster administrators.\n  tags:\n  - OpenShift\n  - Kubernetes\n  - Platform\n  - DevOps\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    OPENSHIFT_TOKEN: OPENSHIFT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: rest-api\n    baseUri: https://api.openshift.com\n    description: OpenShift REST API for cluster and resource management.\n    authentication:\n      type: bearer\n      token: '{{OPENSHIFT_TOKEN}}'\n    resources:\n    - name: platform\n      path: /\n      description: OpenShift platform resources\n      operations:\n      - name: list-projects\n        method: GET\n        description: List OpenShift projects\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-project\n        method: GET\n        description: Get project details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-builds\n        method: GET\n        description: List builds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-routes\n        method: GET\n        description: List routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-deployments\n        method: GET\n        description: List deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-pods\n        method: GET\n        description: List pods\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pod\n        method: GET\n        description: Get pod details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-services\n        method: GET\n        description: List services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-configmaps\n        method: GET\n        description: List config maps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-nodes\n        method: GET\n        description: List nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-operators\n\
  \        method: GET\n        description: List operators\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-images\n        method: GET\n        description: List image streams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-storage\n        method: GET\n        description: List persistent volumes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: platform-management-api\n    description: Unified REST API for OpenShift platform management.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Project management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List projects\n        call:\
  \ rest-api.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: platform-management-mcp\n    transport: http\n    description: MCP server for AI-assisted OpenShift platform management.\n    tools:\n    - name: list-projects\n      description: List OpenShift projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Get project details\n      hints:\n        readOnly: true\n      call: rest-api.get-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-builds\n      description: List builds\n      hints:\n        readOnly: true\n      call: rest-api.list-builds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-routes\n      description: List routes\n      hints:\n        readOnly:\
  \ true\n      call: rest-api.list-routes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deployments\n      description: List deployments\n      hints:\n        readOnly: true\n      call: rest-api.list-deployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pods\n      description: List pods\n      hints:\n        readOnly: true\n      call: rest-api.list-pods\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pod\n      description: Get pod details\n      hints:\n        readOnly: true\n      call: rest-api.get-pod\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-services\n      description: List services\n      hints:\n        readOnly: true\n      call: rest-api.list-services\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-configmaps\n      description: List config maps\n      hints:\n        readOnly:\
  \ true\n      call: rest-api.list-configmaps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nodes\n      description: List cluster nodes\n      hints:\n        readOnly: true\n      call: rest-api.list-nodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-operators\n      description: List installed operators\n      hints:\n        readOnly: true\n      call: rest-api.list-operators\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-images\n      description: List image streams\n      hints:\n        readOnly: true\n      call: rest-api.list-images\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-storage\n      description: List persistent volumes\n      hints:\n        readOnly: true\n      call: rest-api.list-storage\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
