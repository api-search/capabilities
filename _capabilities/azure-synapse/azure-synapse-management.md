---
consumed_apis:
- azure-synapse
description: Workflow capability for managing Azure Synapse Analytics resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Synapse Analytics Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Synapse Analytics
provider_slug: azure-synapse
search_terms:
- list
- sql
- azure
- cloud
- list workspace resources
- list sql pools
- list all resources
- azure resource management
- management
- apache spark
- list workspaces
- list bigdatapool resources
- data warehouse
- etl
- list pipeline resources
- list sqlpool resources
- list pipelines
- analytics
- big data
- list big data pools
- resource management
slug: azure-synapse-management
tags:
- Azure
- Cloud
- Management
tools:
- description: List Workspace resources
  hints:
    openWorld: true
    readOnly: true
  name: list-workspaces
- description: List SqlPool resources
  hints:
    openWorld: true
    readOnly: true
  name: list-sql-pools
- description: List BigDataPool resources
  hints:
    openWorld: true
    readOnly: true
  name: list-big-data-pools
- description: List Pipeline resources
  hints:
    openWorld: true
    readOnly: true
  name: list-pipelines
---
