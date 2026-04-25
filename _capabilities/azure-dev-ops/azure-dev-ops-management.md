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
- list pipeline resources
- list project resources
- devops
- azure resource management
- list all resources
- list organizations
- version control
- list projects
- resource management
- azure
- list repositorys
- management
- cloud
- ci/cd
- list organization resources
- project management
- list
- list pipelines
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
