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
- azure resource management
- list tasks
- azure
- registry
- resource management
- list all resources
- list
- list webhook resources
- list task resources
- management
- docker
- list webhooks
- cloud
- list registry resources
- list registrys
- containers
- container images
- list replications
- list replication resources
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
