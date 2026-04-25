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
- list
- list functions
- azure
- cloud
- list configurations
- list configuration resources
- list all resources
- azure resource management
- management
- list deployments
- list deployment resources
- list functionapp resources
- serverless
- list function apps
- functions
- list function resources
- faas
- compute
- resource management
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
