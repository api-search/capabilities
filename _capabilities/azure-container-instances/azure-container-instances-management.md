---
consumed_apis:
- azure-container-instances
description: Workflow capability for managing Azure Container Instances resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Container Instances Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Container Instances
provider_slug: azure-container-instances
search_terms:
- list all resources
- containers
- azure resource management
- azure
- list containergroupusage resources
- container instances
- list containers
- serverless
- cloud
- list containergroup resources
- microsoft
- resource management
- list container resources
- list container group usages
- list
- management
- list container groups
slug: azure-container-instances-management
tags:
- Azure
- Cloud
- Management
tools:
- description: List ContainerGroup resources
  hints:
    openWorld: true
    readOnly: true
  name: list-container-groups
- description: List Container resources
  hints:
    openWorld: true
    readOnly: true
  name: list-containers
- description: List ContainerGroupUsage resources
  hints:
    openWorld: true
    readOnly: true
  name: list-container-group-usages
---
