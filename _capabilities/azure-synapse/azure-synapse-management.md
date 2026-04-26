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
- list pipelines
- sql
- analytics
- big data
- data warehouse
- cloud
- list all resources
- management
- resource management
- list workspaces
- apache spark
- list big data pools
- list sqlpool resources
- list pipeline resources
- list bigdatapool resources
- etl
- list sql pools
- azure
- list workspace resources
- azure resource management
- list
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
