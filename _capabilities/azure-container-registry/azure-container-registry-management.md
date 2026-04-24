---
consumed_apis:
- azure-container-registry
description: Workflow capability for managing Azure Container Registry resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Container Registry Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Container Registry
provider_slug: azure-container-registry
search_terms:
- registry
- list replications
- list registry resources
- list all resources
- cloud
- list replication resources
- list tasks
- list webhooks
- azure resource management
- list registrys
- resource management
- management
- container images
- list
- containers
- list webhook resources
- list task resources
- azure
- docker
slug: azure-container-registry-management
tags:
- Azure
- Cloud
- Management
tools:
- description: List Registry resources
  hints:
    openWorld: true
    readOnly: true
  name: list-registrys
- description: List Replication resources
  hints:
    openWorld: true
    readOnly: true
  name: list-replications
- description: List Webhook resources
  hints:
    openWorld: true
    readOnly: true
  name: list-webhooks
- description: List Task resources
  hints:
    openWorld: true
    readOnly: true
  name: list-tasks
---
