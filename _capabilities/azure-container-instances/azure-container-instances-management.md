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
- resource management
- list container group usages
- microsoft
- list containers
- list all resources
- list
- list containergroupusage resources
- cloud
- list container groups
- containers
- azure resource management
- container instances
- serverless
- azure
- management
- list container resources
- list containergroup resources
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
