---
consumed_apis:
- azure-function-apps
description: Workflow capability for managing Azure Function Apps resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Function Apps Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Function Apps
provider_slug: azure-function-apps
search_terms:
- azure resource management
- compute
- azure
- resource management
- list all resources
- list
- serverless
- management
- list configuration resources
- list function apps
- list configurations
- cloud
- list function resources
- list functionapp resources
- list deployment resources
- list deployments
- faas
- list functions
- functions
slug: azure-function-apps-management
tags:
- Azure
- Cloud
- Management
tools:
- description: List FunctionApp resources
  hints:
    openWorld: true
    readOnly: true
  name: list-function-apps
- description: List Function resources
  hints:
    openWorld: true
    readOnly: true
  name: list-functions
- description: List Deployment resources
  hints:
    openWorld: true
    readOnly: true
  name: list-deployments
- description: List Configuration resources
  hints:
    openWorld: true
    readOnly: true
  name: list-configurations
---
