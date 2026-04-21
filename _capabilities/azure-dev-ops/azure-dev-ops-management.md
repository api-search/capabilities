---
consumed_apis:
- azure-dev-ops
description: Workflow capability for managing Azure DevOps resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure DevOps Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure DevOps
provider_slug: azure-dev-ops
search_terms:
- list repository resources
- project management
- list projects
- list repositorys
- list organizations
- azure
- list project resources
- management
- list pipeline resources
- cloud
- version control
- devops
- list all resources
- ci/cd
- list organization resources
- list pipelines
- resource management
- list
- azure resource management
slug: azure-dev-ops-management
tags:
- Azure
- Cloud
- Management
tools:
- description: List Pipeline resources
  hints:
    openWorld: true
    readOnly: true
  name: list-pipelines
- description: List Project resources
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: List Organization resources
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List Repository resources
  hints:
    openWorld: true
    readOnly: true
  name: list-repositorys
---
