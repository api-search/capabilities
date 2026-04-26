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
- list pipelines
- list repositorys
- project management
- list organization resources
- cloud
- list all resources
- list repository resources
- list organizations
- management
- resource management
- list project resources
- list pipeline resources
- version control
- devops
- azure
- azure resource management
- list projects
- ci/cd
- list
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
