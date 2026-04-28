---
categories:
- runtime
- discovery
consumed_apis:
- containerd-grpc
description: List and inspect images and running containers in a containerd runtime — needed when a developer environment ships custom MCP and Qdrant images for AI tooling and the platform team needs an inventory. Read-heavy introspection so a technical writer or platform engineer can confirm what is actually running behind their AI-assisted docs pipeline.
layout: capability
name: containerd Runtime Image Introspection
operations:
- description: List all images in the containerd image store
  method: GET
  name: list-images
  path: /v1/images
- description: Get the OCI config for a specific image including labels and entrypoint
  method: GET
  name: get-image-config
  path: /v1/images/{name}
- description: List all containers managed by containerd
  method: GET
  name: list-containers
  path: /v1/containers
- description: Get current status of a specific container including task state
  method: GET
  name: get-container-status
  path: /v1/containers/{id}
- description: Pull an image into the containerd image store
  method: POST
  name: pull-image
  path: /v1/images/pull
- description: Prune unused images to reclaim disk in a developer environment
  method: POST
  name: prune-images
  path: /v1/images/prune
personas:
- Platform Engineer
- API Architect
provider_name: containerd
provider_slug: containerd
search_terms:
- list containerd images
- get image config
- list containers
- get container status
- pull image
- prune unused images
- mcp image inventory
- qdrant image inventory
- developer environment introspection
- ai tooling runtime
- platform engineer image audit
- custom mcp images
- docker containerd ai dev
- runtime image discovery
- oci config inspection
- container task state
- image store reclaim
- container runtime governance
- list running containers
- platform team inventory
slug: runtime-image-introspection
tags:
- containerd
- Runtime
- Images
- Containers
- Platform
tools:
- description: List all images in the containerd image store including custom MCP and Qdrant images
  hints:
    openWorld: false
    readOnly: true
  name: list-images
- description: Get the OCI config for a specific image including labels, entrypoint, and exposed ports
  hints:
    openWorld: false
    readOnly: true
  name: get-image-config
- description: List all containers managed by containerd to inventory the developer environment
  hints:
    openWorld: false
    readOnly: true
  name: list-containers
- description: Get current status of a specific container including task state and exit code
  hints:
    openWorld: false
    readOnly: true
  name: get-container-status
- description: Pull an image into the containerd image store from a remote registry
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: pull-image
- description: Prune unused images to reclaim disk in a developer environment with many AI tool builds
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: prune-images
---
